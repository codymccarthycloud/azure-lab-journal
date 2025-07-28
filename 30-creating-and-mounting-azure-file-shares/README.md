# Azure Lab Journal: Creating and Mounting Azure File Shares

## Lab Overview
- **Goal:** Create an Azure File Share and mount it on a Linux VM running in Azure
- **Tools Used:** Azure Portal, Azure CLI, SSH, `cifs-utils`, Linux VM
- **Storage Account Name:** linuxazlabvrfqpshztezc6
- **File Share Name:** fileshare1
- **VM Public IP:** 74.235.254.141
- **VM Username:** azureuser

---

## Step 1: Create a File Share in Azure Storage Account

1. Go to Azure Portal
2. Navigate to **Storage accounts**
3. Select your storage account: `linuxazlabvrfqpshztezc6`
4. Click **File shares** > `+ File share`
5. Name: `test-eus-stg-vmfiles-labvm`
6. Quota: `100 TiB`
7. Click **Create**

---

## Step 2: Configure and Access Your Linux VM

1. Navigate to **Virtual Machines** and locate your VM
2. Use **Reset password** to inject SSH key
3. Open Azure **Cloud Shell** and run:

```bash
   ssh-keygen
   cat ~/.ssh/id_ed25519.pub
```
Paste public key into VM's SSH field

SSH into VM:

```bash
ssh -i .ssh/id_ed25519 azureuser@74.235.254.141
```
- Login using the public IP Address from the VM

---

## Step 3: Prepare Linux VM for Mounting

Update system packages and install CIFS utilities:

```bash
sudo apt update
sudo apt install cifs-utils
```
Create a local mount point directory for your file share on the VM:

```bash
sudo mkdir /mnt/test-eus-stg-vmfiles-labvm
```
---

## Step 4: Mount the Azure File Share

In the Azure Portal:

- Go to your Storage Account
- Click **Access keys** and copy **key1**
- Open **File share** > **Properties** and copy the SMB path (skip the `https:`)

Run the mount command:

```bash
sudo mount -t cifs //linuxazlabvrfqpshztezc6.file.core.windows.net/fileshare1 \
/mnt/test-eus-stg-vmfiles-labvm \
-o vers=3.0,username=linuxazlabvrfqpshztezc6,password=<your_storage_account_key>,dir_mode=0777,file_mode=0777,serverino
```

---

Step 5: Verify Mount and Create a File

Confirm the file share is mounted:
```bash
df -h
```
Create a new file in the mounted share:
```bash
cd /mnt/test-eus-stg-vmfiles-labvm
touch file1.txt
```

Open the Azure Portal > Navigate to your Storage Account 
> Go to the File Share Confirm that file1.txt is visible 
— indicating the mount is successful and syncing with Azure

---

### Summary

- Mounted Azure File Share to your Linux VM using SMB
- Created a local mount point at /mnt/test-eus-stg-vmfiles-labvm
- Any changes (like touch file1.txt) are instantly synced to Azure
- Optional fstab entry ensures remounting after reboot
- No need for Azure Arc — this setup is entirely native to Azure

---

### (Optional): Make Mount Persistent After Reboot
Open the fstab configuration file:

```bash
sudo nano /etc/fstab
Add this line:
```

```plaintext
//linuxazlabvrfqpshztezc6.file.core.windows.net/fileshare1 /mnt/test-eus-stg-vmfiles-labvm cifs vers=3.0,username=linuxazlabvrfqpshztezc6,password=<your_storage_account_key>,dir_mode=0777,file_mode=0777,serverino 0 0
```

Tip: For better security, use a credentials file instead of placing your password directly in /etc/fstab.

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/1cb4218a-d88c-4272-881d-a3152041c4de)
![2](https://github.com/user-attachments/assets/9fdaa7cc-35b0-4700-a938-088b247d8ee8)
![3](https://github.com/user-attachments/assets/90f2a169-a1b0-4b7f-b5ed-4bebefe4cffd)
![4](https://github.com/user-attachments/assets/69815726-f716-4031-81e4-3c885fb698fb)
![5](https://github.com/user-attachments/assets/cd84a5ba-1f39-4b18-9ce0-0cc34cf3647c)
![6](https://github.com/user-attachments/assets/8599cb00-d893-4193-871f-f050eb35e113)
![7](https://github.com/user-attachments/assets/0a0d1e77-f2f5-463d-a6d5-c922390e9fdc)
![8](https://github.com/user-attachments/assets/aea1011f-85d3-4862-9065-3ab1f0b5c3d9)
![9](https://github.com/user-attachments/assets/ae3abba7-b4b6-47cd-a0a3-69b820f4d36f)
![10](https://github.com/user-attachments/assets/faba3d3a-eddb-4f40-a80a-67f6f3fbc60e)

