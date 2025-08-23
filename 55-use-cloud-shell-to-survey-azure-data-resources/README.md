# Use Cloud Shell to Survey Azure Data Resources

## Lab Overview

You're a new team member with read-only access to the QA Azure subscription. 
Your mission: **inventory the data resources** and compare them with the team's documentation. 

This lab guides you through three methods:
- Azure Portal
- PowerShell in Cloud Shell
- Azure CLI in Cloud Shell

---

## Getting Started
- Open the Azure Portal in **Incognito mode**
- Use the **lab-provided credentials**
- Navigate to the **resource group** assigned in the lab

---

## Method 1: Survey via Azure Portal

### Steps:
1. Open the **Dashboard** from the hamburger menu
2. Navigate to the **resource group**
3. Click the **SQL Server instance**
   - Review: Essentials, Activity Log, Access Control (IAM)
4. Click the **Storage Account**
   - Review: Essentials, Activity Log, Access Control (IAM)
5. Navigate to **Containers**
   - Open the listed blob container (should be empty)

---

## Method 2: Survey Using PowerShell in Cloud Shell

### Setup:
1. Click the **Cloud Shell icon** ( >_ )
2. Select **PowerShell**
3. Click **Show advanced settings**
   - Use the same location as the resource group
   - Create a new Storage Account (globally unique name)
   - Create a new File Share (any name)
4. Click **Create storage**

### Commands:
```powershell
# List all resources in table format
Get-AzResource | ft

# Filter for SQL databases
Get-AzResource -ResourceType Microsoft.Sql/servers/databases | fl

# Filter for Cosmos DB resources
Get-AzResource -Name *cosmos* | fl -Property *
```

Method 3: Survey Using Azure CLI in Cloud Shell
Setup:
Switch to Bash terminal

Confirm the switch when prompted

Commands:

```bash
# List all resources in table format
az resource list --output table

# Filter for SQL databases
az resource list --resource-type 'Microsoft.Sql/Servers/databases' --output table

# Same command with YAML output
az resource list --resource-type 'Microsoft.Sql/Servers/databases' --output yaml

# Filter for Cosmos DB using query syntax
az resource list --query "[?contains(name, 'cosmos')]" --output yaml
```

### Learning Objectives
- Navigate Azure Portal to inspect data resources
- Use PowerShell and Azure CLI to query Azure resources
- Understand basic resource metadata and access controls

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/8ecddb40-ad3a-46eb-ace6-c8f16247d924)
![2](https://github.com/user-attachments/assets/1a9fd8d3-8ee9-4f0b-afab-e8105bcd9203)
![3](https://github.com/user-attachments/assets/9eded771-648b-4215-8b91-998c213e9443)
![4](https://github.com/user-attachments/assets/3c7690bf-a1f1-48c7-833c-d8e9ff836b4b)
![5](https://github.com/user-attachments/assets/f93dbb25-63ca-4cb5-989e-99a1c7373a0b)
![6](https://github.com/user-attachments/assets/40e8d27c-6ac5-4519-b375-c9a3282515a6)
![7](https://github.com/user-attachments/assets/01ae591f-7608-44aa-b8d9-e3d58817dc1c)
![8](https://github.com/user-attachments/assets/c2e35c1c-8918-4b95-9f1e-dfcdcdc72606)
![9](https://github.com/user-attachments/assets/4a1fea63-d8f5-4b3c-bfe1-50898b8932fc)
![10](https://github.com/user-attachments/assets/6e42bd8c-0b31-4068-b0ff-7f70488edf12)
![11](https://github.com/user-attachments/assets/f8aa9d99-c118-4f28-a70d-27838950db9d)
![12](https://github.com/user-attachments/assets/c2a35135-a78a-4ab8-8464-c26601eb1df8)
![13](https://github.com/user-attachments/assets/46a5ba4e-1c56-4a5f-8ef9-8f32255b3625)
![14](https://github.com/user-attachments/assets/0d648015-64a0-4538-a918-7d2c36755768)



