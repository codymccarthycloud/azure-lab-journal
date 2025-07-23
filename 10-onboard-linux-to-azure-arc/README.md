# Lab: Onboard Linux to Azure Arc


## Overview

This lab demonstrates how to onboard a Linux VM into Azure Arc by:
- Generating the onboarding script from Azure Portal
- Connecting via SSH to the Linux VM
- Executing the script to register the machine with Azure Hybrid Compute

---

## Step 1: Lab Credentials

### Azure Portal Account (for accessing Azure resources)
- Username: cloud_user_p_c5c5f803@realhandsonlabs.com
- Password: ^4+G%*58

### Linux VM Login (for SSH access)
- Username: cloud_user
- Password: BixusD8NBb1JW@GdYoTy
- Public IP: 20.253.202.64

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
- VM appeared in Azure Portal under Hybrid Compute 
- Azure management

---

## Lab Output Screenshots





