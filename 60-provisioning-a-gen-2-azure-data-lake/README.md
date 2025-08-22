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

![1](https://github.com/user-attachments/assets/2b2ff601-8157-4177-bebc-574270562b82)
![2](https://github.com/user-attachments/assets/555b5c75-261f-41f2-982e-7ff47bf5d877)
![4](https://github.com/user-attachments/assets/257012c7-5529-44ad-b868-1b1ae57d5992)
![5](https://github.com/user-attachments/assets/67579cea-2a00-49dd-86e8-03a5a28b0549)
![6](https://github.com/user-attachments/assets/645ca682-6ba3-498c-911c-6c5bdf274e3f)
![7](https://github.com/user-attachments/assets/c97a5a7d-d9c2-4305-a359-5e7aa0052bb3)
![8](https://github.com/user-attachments/assets/eb87098a-18ce-4a4c-ae9d-85d92d86c294)
![3](https://github.com/user-attachments/assets/67dc84c7-9eea-4dbf-aca5-720760dfdb20)
![12](https://github.com/user-attachments/assets/c990976c-35c9-4a67-ac6e-50717021a18a)
![13](https://github.com/user-attachments/assets/38a07952-2be3-4197-95f1-e12f6690b883)
![14](https://github.com/user-attachments/assets/4b376fe2-a002-439e-a278-6e9a3bc6ed4a)
![15](https://github.com/user-attachments/assets/69150658-309f-46d7-b84d-fc81e3c3cc36)



