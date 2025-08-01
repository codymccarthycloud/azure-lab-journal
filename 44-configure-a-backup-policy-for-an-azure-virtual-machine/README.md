# Configure a Backup Policy for an Azure Virtual Machine

## Learning Objectives

1. Create and configure a Recovery Services vault.  
2. Define a custom Backup policy for Azure Virtual Machines.  
3. Enable backup for an existing VM (vm1) using your new policy.  

## Lab Tasks

### 1. Create a Recovery Services Vault

1. Sign in to the Azure portal with your lab credentials in a private/incognito window.  
2. Launch **Cloud Shell** (Bash) or use the portal GUI.  
3. Navigate to **Recovery Services vaults** and click **+ Create**.  
4. On the **Basics** tab:
   - **Subscription:** Select your lab subscription.  
   - **Resource group:** Select the existing resource group.  
   - **Vault name:** `vault1`  
   - **Region:** Same region as your pre-deployed VM.  
5. Click **Review + create**, then **Create**.  

### 2. Create a Backup Policy

1. After the vault deploys, open **Recovery Services vaults** → **vault1**.  
2. In the left menu, select **Backup policies**.  
3. Click **+ Add** and choose:
   - **Policy type:** Azure Virtual Machine  
   - **Policy sub-type:** Standard  
4. Configure the policy settings:
   - **Policy name:** `NightlyVMBackup`  
   - **Frequency:** Daily  
   - **Time:** 9:00 PM  
   - **Timezone:** Your local timezone  
   - **Instant Restore:** 1 Day  
   - **Retention of daily backup point:** 7 Days  
   - **Retention of weekly/monthly/yearly backup points:** Unchecked  
   - **Azure Backup Resource Group:** Leave blank  
5. Click **OK** to save the new policy.  

### 3. Enable Backups for VM1

1. In the portal, navigate to the virtual machine named **vm1**.  
2. In the left menu under **Operations**, click **Backup**.  
3. On the **Backup** pane:
   - **Recovery Services vault:** Select `vault1`  
   - **Backup policy:** Select `NightlyVMBackup`  
4. Click **Enable backup**.  

## Additional Information

- To trigger an on-demand backup, use **Backup now** from the vault or VM blade.  
- Perform a full VM restore via **Restore VM** when needed.  
- Use **File Recovery** to extract individual files without a full VM restore.  
- Different Azure Backup solutions (VM direct, in-guest agent, etc.) present unique backup/restore workflows.  

---

## Lab Output Screenshots

![1 it is a vm](https://github.com/user-attachments/assets/6994d977-86bf-42f2-a83c-cae524827596)
![2 backup recovery services vault backup for vm](https://github.com/user-attachments/assets/78eeb6e3-2342-452a-a21c-bf462b3657b8)
![3 recovery services manage backup policies](https://github.com/user-attachments/assets/30c70608-3b18-4500-8325-0a5defe02ff1)
![4 back up policy create a vm backup policy](https://github.com/user-attachments/assets/dce89322-b490-46d1-8ba2-60bfaef41d7a)
![5 virtual machine create vm backup policy](https://github.com/user-attachments/assets/32086069-de53-401c-8b65-ef051cb77564)
![6 virtual machine backup choose backup vault and backup policy nightly backup](https://github.com/user-attachments/assets/806d6d75-b144-4942-9176-a64005b88cb4)
![7 backup policies nightlyvmbackup](https://github.com/user-attachments/assets/eb4c9274-1433-4a53-9d5f-d3a01a0eda67)
![8 recovery services vault overview backup](https://github.com/user-attachments/assets/0012db42-185e-4816-b07e-24e2acb464ac)
![9 backup](https://github.com/user-attachments/assets/499dc127-846b-46e7-8c82-8ab4d156f92b)








