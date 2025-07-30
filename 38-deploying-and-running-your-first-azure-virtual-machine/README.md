# Deploying and Running Your First Azure Virtual Machine

This lab walks through the creation, connection, and management of your first virtual machine (VM) in Azure, using Windows Server 2019 Datacenter.

---

## Learning Objectives
1. Log in to the Azure Portal using provided credentials.
2. Create a new Windows Server 2019 Datacenter VM.
3. Connect to the VM using RDP (Remote Desktop Protocol).
4. Stop and verify the VM’s shutdown state.

---

## Lab Steps

### 1. Create a Virtual Machine
- Navigate to **Virtual machines** in the Azure dashboard.
- Choose:
  - **Image**: Windows Server 2019 Datacenter - Gen 2
  - **Region**: Same as the provided resource group
  - **Username**: `acg-admin`
  - **Password**: `Admin123456!`
- Deploy the VM.

### Deployment
- VM deployment
- Disk deployment
- VNet deployment
- Subnet IP deployment 
- Public IP deployment
- Network Security Group deployment


### 2. Connect via Remote Desktop
- In the VM panel, click **Connect** → **RDP**.
- Download the `.rdp` file and open it using your Remote Desktop client.
- Authenticate using the VM credentials.

### 3. Stop the Virtual Machine
- In Azure Portal, locate your VM.
- Click **Stop** and confirm the status changes to **Stopped (deallocated)**.

---

## Lab Output Screenshots

![1 create a vm subnet public ip set nsg to basic](https://github.com/user-attachments/assets/f6008aa8-8035-481f-8736-dbdcd669dd29)
![2 create vnet subnet public ip delete with vm](https://github.com/user-attachments/assets/a7742378-b39c-445c-af39-a41b85c4356a)
![3 create vm disk vnet subnet public ip basic nsg](https://github.com/user-attachments/assets/eda12289-1c71-4720-be73-113eb59fd85f)
![4 login using the rdp to the vm with the public ip](https://github.com/user-attachments/assets/379b0df1-0943-4180-b1f9-49fe7b7f239f)
![5 using rdp login with the vm public id created using username and password](https://github.com/user-attachments/assets/9f01c564-9268-481e-a9df-4df3e6e2e1fa)
![6 logged in using rdp to the vm](https://github.com/user-attachments/assets/18895f16-3335-45b2-80c8-e8e4a371a7ea)




