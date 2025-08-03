# Configure and Connect to Azure Files from Windows

---

## Learning Objectives
- Create an Azure Files share in the Azure portal
- Connect to a Windows VM using RDP
- Map the Azure Files share using PowerShell
- Verify centralized file storage

---

### 1. Create an Azure Files Share

1. Go to **Storage Accounts** in the Azure portal.
2. Open the pre-created storage account.
3. In the left pane, click **File shares**.
4. Click **+ File share**.
5. Name the share `companydata` and leave **Quota** blank (no quota).
6. Click **Create**.

---

### 2. Connect to Windows VM via RDP

1. Navigate to **Virtual Machines** in the Azure portal.
2. Select the VM named `vm1`.
3. Click **Connect** > **RDP**.
4. Download the RDP file or copy the public IP to connect manually.
5. Use the following credentials:
   - **Username**: `azureuser`
   - **Password**: `$OYh0m7aQIaQtA6NAGkZ`

---

### 3. Map Azure Files Share Using PowerShell

1. In the Azure portal, go back to the **Storage Account**.
2. Click **File shares** > select `companydata`.
3. Click **Connect** in the command bar.
4. Copy the **Windows PowerShell script** provided.
5. On the VM, open PowerShell:

Start > Windows PowerShell > Windows PowerShell

6. Paste and run the script to map the file share (usually to drive `Z:`).

---

### 4. Verify File Share Connection

1. Open **Windows Explorer** > **This PC**.
2. Access the mapped `Z:` drive.
3. Create folders and files.
4. Go back to the Azure portal and open the file share to confirm the files are stored centrally.

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/bb56af89-4489-4d4c-b208-e8beba55c25d)
![2](https://github.com/user-attachments/assets/02830793-34b4-47db-bbaa-0a06bf062c25)
![4](https://github.com/user-attachments/assets/8ecc8ad2-9d83-4003-b0fb-c4f4d0a1c44a)
![3](https://github.com/user-attachments/assets/591aa0f7-4993-41e0-9f56-dfb3068da487)
![5](https://github.com/user-attachments/assets/cdb2a03a-3829-4a00-870d-400152104ca7)
![6](https://github.com/user-attachments/assets/779d9e2c-031c-4078-8022-3d5827c36497)
![7](https://github.com/user-attachments/assets/d25544a0-c478-4be5-8e96-9ed109e074f7)
![8](https://github.com/user-attachments/assets/45252e3f-1353-4d77-8625-366647b1e210)
![9](https://github.com/user-attachments/assets/4ba7ce76-59ae-4a3e-8e62-cdadf0c04f45)
![10](https://github.com/user-attachments/assets/90f8f464-1055-40f6-96c9-4e70bf0324dd)
![11](https://github.com/user-attachments/assets/e23028b2-2aa0-4507-ba79-9cd1d0d0e5dd)
![12](https://github.com/user-attachments/assets/e84aa14e-89eb-4dad-92ca-cb4b67448f18)
![13](https://github.com/user-attachments/assets/207288ac-49ac-4915-bd9a-66219c2a05cc)
![14](https://github.com/user-attachments/assets/9ad1ff05-4274-4369-a37f-8e953567f90c)
![15](https://github.com/user-attachments/assets/f8e99b73-8d94-4eba-8546-cda3df28026d)
![16](https://github.com/user-attachments/assets/98ed9195-6522-4e97-a59a-792316074b53)
