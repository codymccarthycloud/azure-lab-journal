## Provisioning a Gen 2 Azure Data Lake
This guide walks you through provisioning an Azure Data Lake Gen2 Storage account with 
hierarchical namespace enabled and implementing a zoned folder structure using the Azure portal.

## Provision a Gen2 Azure Data Lake Instance

In the Azure portal dashboard: 

- Click All resources > Add > Storage > Storage accounts.
- Click + Create storage account.
- Configure the following settings:
- Resource group: Select the existing resource group.
- Storage account name: eussa96c553 
- Location: (US) East US.
- Primary Service: Azure Blob Storage or Azure Data Lake Storage Gen 2
- Performance: Standard.
- Replication: Read-access geo-redundant storage (RA-GRS).
- Access tier: Hot.
- Set Hierarchical namespace to Enabled.
- Review + create, and then click Create.

## Implement a Zoned Folder Structure

- When deployment finishes, click Go to resource.
- In the storage account’s left menu, select Storage Explorer (preview).
- Right-click CONTAINERS and choose Create file system.
- Name the file system test and click OK.
- Select the test file system to open it.
- Click + New Folder, name it Raw, and click OK.
- Click + New Folder, name it Processed, and click OK.
- Double-click the Raw folder, then create nested folders in sequence:
- Application 1
- Inside Application 1, create 2025
- Inside 2025, create August
- Confirm that the path reads Raw > Application 1 > 2025 > August 

### Conclusion
Created an Azure Data Lake Gen2 Storage account successfully with hierarchical namespace enabled and implemented a zoned folder structure.

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/ae819f1c-afee-4ef6-a668-328abf6a8a1c)
![2](https://github.com/user-attachments/assets/cec90944-a82e-44f1-8b3d-6c7dc62f7611)
![4](https://github.com/user-attachments/assets/b81d3030-f29c-423d-8256-f8ffdc1dab65)
![5](https://github.com/user-attachments/assets/6226e486-2e7e-47c4-afd2-e79a0739bbf2)
![6](https://github.com/user-attachments/assets/f3db555e-a7ea-47f4-b7de-bf528f5de3bd)
![7](https://github.com/user-attachments/assets/1982ac33-6012-4ae2-aa26-6ed58c1e6417)
![8](https://github.com/user-attachments/assets/5d3066f0-4b21-413d-8fae-7c78a0a83d3a)
![9](https://github.com/user-attachments/assets/5b07ed94-e8af-4d34-be3a-6ce6976ba917)
![10](https://github.com/user-attachments/assets/857910c9-4ea1-4519-bfa3-5235c5449bc6)
![11](https://github.com/user-attachments/assets/22f754ba-ee91-40ca-81f2-0533193b0fdf)
![3](https://github.com/user-attachments/assets/8b46c1e5-271e-482a-927f-46cfbb7d3289)
![12](https://github.com/user-attachments/assets/174b823b-a772-4cf3-bd1f-544a4d01a1f5)
![13](https://github.com/user-attachments/assets/88d92a79-2fa5-407c-aa45-f1245db43228)
![14](https://github.com/user-attachments/assets/2ebba33b-d1c3-435d-b33a-e0ae15387850)
![15](https://github.com/user-attachments/assets/66bba79f-1ff4-4695-b03c-61771b2cabee)


