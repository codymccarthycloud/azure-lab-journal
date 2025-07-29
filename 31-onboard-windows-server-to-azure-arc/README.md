# Onboarding Windows Server to Azure Arc

This lab demonstrates how to onboard a Windows Server virtual machine to Azure Arc, enabling centralized management and governance through the Azure portal.

## Azure Portal Info
- **Resource Group**: `1126-1e4bde14-onboard-windows-server-to-azure-arc`
- **Azure Account**: `cloud_user_p_46bc13dc@realhandsonlabs.com`
- **VM FQDN**: `WinVM1`
- **Private IP**: `10.0.0.4`
- **Public IP**: `57.152.87.33`

## Steps to Complete

### 1. Generate Windows Onboarding Script
- In the Azure portal, navigate to **Azure Arc > Servers > Add**.
- Choose the **Add a single server** option.
- Follow the wizard to generate a **Windows onboarding PowerShell script**.
- Save the script locally.

### 2. Execute Onboarding Script
- Connect to `WinVM1` using Remote Desktop Protocol (RDP).
- Use the credentials provided:
  - **Username**: `cloud_user`
  - **Password**: `yoO4T3sTAoNHRsKMH6I$`
- Launch PowerShell as Administrator.
- Run the onboarding script.

> Tip: If your PC is domain-joined, prefix the RDP username with `.\\`, like `.\\cloud_user`.

### 3. Review Azure Arc-enabled Machine
- Once onboarding completes, navigate to **Azure Arc > Servers**.
- Locate the newly registered machine.
- Review connected capabilities such as:
  - Inventory and metadata
  - Update management
  - Policy enforcement
  - Security recommendations

## Learning Objectives Completed
- Generate onboarding script
- Onboard Windows Server via RDP
- Validate Arc-enabled server registration

---

## Lab Out Screenshots

![1 naviagte to aazure arc resources machines](https://github.com/user-attachments/assets/c078b762-fb06-4d34-86a7-4a085a5764be)
![2 add a server with azure arc](https://github.com/user-attachments/assets/8a6d8946-013f-4d3f-b934-aed6af99762e)
![3 connect to vm with windows remote desktop connection](https://github.com/user-attachments/assets/22dcebeb-dd25-4194-91af-6800c788936f)
![4 connected rdp vm to azure arc using onboarding script in the vm powershell after logging into our azure](https://github.com/user-attachments/assets/583890ef-6659-4df4-be62-a81ad7cf25fa)
![5 vm connected to azure arc](https://github.com/user-attachments/assets/4a9f7195-a825-41e8-b309-7204b636bfc0)
![6 azure arc connected vm](https://github.com/user-attachments/assets/41a0d657-310b-4735-b50f-355c21517a51)







