# Lab: Deploy Windows Server VM with AD DS 


## Overview

This lab walks through the full deployment of a Windows Server VM, installation of Active Directory Domain Services (AD DS), promotion to Domain Controller, and preparation for identity sync using Microsoft Entra Connect (via web portal).

---

## Step 1: Create and Deploy the Azure VM with NSG

1. Use Azure CLI, Terraform, or Portal to deploy a VM:
   - Image: Windows Server 2022
   - Size: `Standard_B2ms`
   - Resource Group: `ADLab-RG`
   - Location: Choose closest region (e.g. East US)

2. Create an **Advanced Network Security Group (NSG)**:
   - Add inbound rule:
     - **Port**: `3389`
     - **Protocol**: `TCP`
     - **Priority**: `100`
     - **Action**: `Allow`
     - **Source**: `Any` or your IP range
     - **Destination**: VM Private IP

3. Attach NSG to your VM's NIC or subnet.

---

## Step 2: RDP Into the Server

- Copy the **public IP** from Azure Portal
- Open Remote Desktop Connection
- Connect using
  - **IP**: `XXX.XXX.XXX.XXX`
  - **Username**: From deployment
  - **Password**: From deployment

You should see the Windows desktop — don’t close this session.

---

## Step 3: Install AD DS Role

1. Open **Server Manager**
2. Go to **Add Roles and Features**
3. Select:
   - Role-Based → Active Directory Domain Services
   - Add features if prompted
4. Complete the wizard and restart if required  
  Leave the window open after install

---

## Step 4: Promote Server to Domain Controller

1. In Server Manager → Click **"Promote this server to a domain controller"**
2. Choose:
   - Add a new forest
   - Enter domain name (e.g. `cloudlab.local`)
3. Set DSRM password and confirm configuration
4. Complete promotion and reboot VM

   Server will now function as your domain controller

---

## Step 5: Confirm AD DS Services

- After reboot → open **Server Manager**
- Check **Dashboard**:
  - **AD DS** and **DNS** roles listed under “Roles and Server Groups”
  - No red X warnings

  Domain Controller status verified

---

## Step 6: Microsoft Entra Connect (Azure AD Connect Sync)

### Legacy Azure AD Connect Tool Not Available
- Older tools (Azure AD Connect, Microsoft Entra Connect installer) are **deprecated** in lab environments

### Continue via Microsoft Entra ID
1. Go to [https://entra.microsoft.com](https://entra.microsoft.com)
2. Sign in with your Azure subscription credentials
3. Navigate to:
   - **Identity > Synchronization**
   
4. Follow steps to link local AD domain (`cloudlab.local`) to Microsoft Entra ID

---

## Conclusion

 VM deployed with NSG and port 3389 open  
 RDP access confirmed  
 AD DS role installed and promoted to domain controller  
 Services verified via Server Manager  
 Attempt identity sync configured using **Microsoft Entra ID** via web portal
 Investiagte practical routable forst names when prmoting server to domain controller
 Understand UPN for user login in active directory

## Lab Output Screenshots

![create a virtual machine](https://github.com/user-attachments/assets/3cbbbfa4-732c-4998-93ce-c8fa9844c852)
![create a virtual machine deployment](https://github.com/user-attachments/assets/943fdda8-e496-4cd1-b97f-6812402da813)
![create a virtual machine deployed](https://github.com/user-attachments/assets/fcc65606-62da-40fa-b007-be1f43fea488)
![create an inbound security rule allow port 3389 rdp](https://github.com/user-attachments/assets/8e1977b1-5194-4f73-81ae-b4aef71d27e6)

