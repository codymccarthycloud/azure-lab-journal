# Configure a Backup Policy for an Azure Virtual Machine

## Create a Recovery Services Vault
Instructions:
- Log in to the Azure Portal using the lab credentials.
- Note the region of your existing resources.
- Navigate to Create a resource > Search for Recovery Services vault.
- Configure the vault:
- Subscription: Use existing
- Resource Group: Use existing
- Name: Vault1-372
- Region: Same as existing resources
- Click Review + Create, then Create.

## Create a Backup Policy
Instructions:
- After the vault is deployed, open it.
- Go to Backup Policies > Add.
- Set the following:
- Policy Type: Azure Virtual Machine
- Sub-Type: Standard
- Policy Name: NightlyVMBackup
- Frequency: Daily
- Time: 9:00 PM
- Timezone: Your local timezone
- Instant Restore: 1 Day
- Retention (Daily): 7 Days
- Retention (Weekly/Monthly/Yearly): Leave unchecked
- Azure Backup Resource Group: Leave blank
- Save the policy.

## Enable Backups for VM1
Instructions:
- Navigate to the virtual machine named vm1.
- Select Backup from the left menu.
Configure:
- Recovery Services Vault: Vault1-372
- Backup Policy: NightlyVMBackup
- Click Enable Backup.

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/f85fd16e-a909-40c8-8cb1-90894a616ab9)
![2](https://github.com/user-attachments/assets/abf4a138-ba37-487e-8161-b36069eb30cc)
![3](https://github.com/user-attachments/assets/2f2f288f-fadc-4c8f-a80e-ba7a35a30845)
![4](https://github.com/user-attachments/assets/1a7d8b3f-d15f-483c-862a-07f717b36d51)
![5](https://github.com/user-attachments/assets/d3b2e126-69fc-42d4-8ea0-1a6e076b5712)
![6](https://github.com/user-attachments/assets/938f2cab-e7c7-4fd7-aaff-db1ded826bd1)
![7](https://github.com/user-attachments/assets/10622662-78cf-4665-82e3-ee8ad18cfc35)
![8](https://github.com/user-attachments/assets/c4014362-9937-4e3f-829c-6ae3f64b0ffa)
![9](https://github.com/user-attachments/assets/ec533ed5-ad97-4ea3-aef8-c888a2eaad75)
![10](https://github.com/user-attachments/assets/dae02935-caec-4a93-a21c-8bfdb8749cf7)
![11](https://github.com/user-attachments/assets/83dd88b8-886d-4ceb-92e7-d92c01c3bf39)
![12](https://github.com/user-attachments/assets/7aae745e-f388-4cb7-865b-6d123ad94c2e)
![13](https://github.com/user-attachments/assets/63405996-8c8c-4d47-bdd5-b6b98e769f8a)
![14](https://github.com/user-attachments/assets/916447fa-d932-4cd4-9aa7-83cf355b1940)
