# Lab: Onboard Linux to Azure Arc


## Overview

This lab demonstrates how to onboard a Linux VM into Azure Arc by:
- Generating the onboarding script from Azure Portal
- Connecting via SSH to the Linux VM
- Executing the script to register the machine with Azure Hybrid Compute

---

## Step 1: Lab Credentials

### Linux VM Login (for SSH access)
- Username: cloud_user
- Password: ****************
- Public IP: **.***.***.**

 The Linux VM is hosted *outside* Azure and will be onboarded using Azure Arc.

---

## Step 2: Generate Azure Arc Onboarding Script
3. Select:

- Resource type: **Non-Azure machine**
- OS: **Linux**
- Subscription: Use default lab subscription
- Resource group: 1129-69cea9b3-onboard-linux-to-azure-arc
4. Click **Next** until script is generated
5. Copy the shell script to paste into the Linux VM

---

## Step 3: SSH Into Linux VM

Use Bash shell or Azure Cloud Shell:

```bash
ssh cloud_user@20.253.202.64
```
---

## Step 4: Paste and Execute Onboarding Script

- Paste the onboarding script from Step 2 into the Linux VM terminal
- When prompted, use your Azure credentials to authenticate:
  - Username: cloud_user_p_c5c5f803@realhandsonlabs.com
  - Password: ^4+G%*58
- Wait for the agent to finish installing and registering the VM

---

## Step 5: Verify VM in Azure Arc

1. Go to the Azure Portal
2. Open the Resource Group: `1129-69cea9b3-onboard-linux-to-azure-arc`
3. Look under **Azure Arc > Servers**
4. Confirm the VM appears with:
   - Type: `Microsoft.HybridCompute/machines`
   - Status: Connected

---

## Step 6: Review Arc Capabilities

You can now manage the onboarded Linux VM just like an Azure resource:

- Apply Azure Policy
- Use Role-Based Access Control (RBAC)
- Tag and organize VM in resource groups
- Enable Microsoft Defender for threat protection
- Monitor logs and performance with Azure Monitor

---

## Conclusion

- SSH connection succeeded 
- Arc script installed and executed 
- Run azcmagnet connect script line after install to register the machine with azure arc
- VM appeared in Azure Portal under Hybrid Compute 
- Azure management enabled

---

## Lab Output Screenshots

![add create machine azure arc and ssh into the linuxVM with the local ip](https://github.com/user-attachments/assets/cab6efce-c38c-4558-b6db-eafbb812de0a)
![add a server with azure arc copy or download script](https://github.com/user-attachments/assets/a8d16b57-88f1-4ca0-b71c-582b10c9b869)
![onboarding azure arc with the linux vm using the script in cli](https://github.com/user-attachments/assets/d137a3f9-771d-42dc-b991-e4d18440096f)
![ssh login to the linuxVM using the private ip](https://github.com/user-attachments/assets/7db757dd-a9e8-4d62-92b3-cab5526e32d0)
![refresh azure arc machine to check and see if the linuxvm has been enabled](https://github.com/user-attachments/assets/b3c2feec-6e71-4415-8653-af85afe1581a)
![check to see capabilities enabled by azure arc](https://github.com/user-attachments/assets/ee3ed572-b85b-4b4e-bb5f-1da38d357e0e)











