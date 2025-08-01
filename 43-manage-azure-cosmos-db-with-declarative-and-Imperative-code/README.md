# Manage Azure Cosmos DB with Declarative and Imperative Code

## Learning Objectives

1. Initialize Cloud Shell and storage.
2. Export an existing Cosmos DB account’s ARM template and store it as a Template Spec.  
3. Edit the Template Spec to change the default consistency level to Eventual and add a new container named `ExtraLabContainer`.  
4. Deploy the updated Template Spec via Azure CLI and verify changes in the portal.  

## Lab Tasks

### 1. Housekeeping

- Open the Azure portal in an incognito or private window.  
- Log in using the provided lab credentials.  
- Launch Cloud Shell and select Bash.  
- When prompted, choose **Show advanced settings** instead of **Create storage**.  
- Configure a new storage account with a unique name and wait for the prompt to return.  

### 2. Export and Save an ARM Template as a Template Spec

1. Navigate to the pre-deployed Azure Cosmos DB account in the portal.  
2. View the account’s ARM template and start the “Save as Template Spec” wizard.  
3. In the template editor (Cloud Shell editor or Visual Studio Code):  
   - Change `defaultConsistencyLevel` to `Eventual`.  
   - Copy the existing container resource, rename it to `ExtraLabContainer`, and update all references from `LabContainer`.  
4. Complete the wizard and confirm the template is stored in your Template Specs library.  
5. Edit with Visual Studio Code to address any error messages when creating and deploying the Template Spec.

### 3. Deploy Template Spec Using Cloud Shell

1. List existing Template Specs:  
```bash
   az ts list
```

Show details of your new Template Spec:

```bash
az ts show \
  --template-spec /subscriptions/<subID>/resourceGroups/<rg>/providers/Microsoft.Resources/templateSpecs/<specName>/versions/<version>
Deploy the Template Spec to the resource group:
```

```bash
az deployment group create \
  --resource-group 725-777fe44a-manage-azure-cosmos-db-with-declarati \
  --template-spec <specName>@<version> 
```

ex: /versions/v1

---

4. In the portal, confirm that:
- The Cosmos DB account’s consistency level is now Eventual.
- A container named AnotherLabContainer exists in the LabDB database.

---

## Lab Output Screenshots

![Uploading 3 change name of new container.JPG…]()
![4 match id to name change](https://github.com/user-attachments/assets/f5fe8137-7abd-4da5-8691-6b6655d99542)
![5 custom deployment](https://github.com/user-attachments/assets/5827af99-6e78-419e-8534-8dcb29425b08)
![7 import edited tempalte](https://github.com/user-attachments/assets/c0aafc1c-ec48-44ce-a7c6-90b65048eecd)
![6 custom edited template json deployment](https://github.com/user-attachments/assets/701c69d8-7cff-4d3d-b732-c6520d7d1119)
![8 template specs imported edited json template](https://github.com/user-attachments/assets/b39fa252-d818-4054-9d87-eb21bc18a268)
![9 az ts list](https://github.com/user-attachments/assets/3e32fe81-0ceb-46e2-a96d-01e881f99a33)
![10 az ts show template spec](https://github.com/user-attachments/assets/ada8ed5c-9d9c-45d2-8c18-e7a35a0ea789)
![11 edit priority level](https://github.com/user-attachments/assets/0872e7cc-6b00-4dfc-bb70-ef068adf7f6a)
![12 visual studio code edit json deployment](https://github.com/user-attachments/assets/4be1ea02-8aff-4322-8d16-f96746512cd1)
![13 cli az ts list az ts show g template spec versions v1](https://github.com/user-attachments/assets/5dacaf04-90fe-47d3-b628-6bcd94d1fb78)
![14 deployment create group g ts versions v1 successful](https://github.com/user-attachments/assets/c9789671-1dff-4920-91d7-d9a17a443dbb)
![15 check the created cosmos db to see if the extra container was added](https://github.com/user-attachments/assets/93d5fb1b-2741-4650-bfff-4827fb0ea2dc)
![16 check to see is the template spec and cosmos db deployed](https://github.com/user-attachments/assets/3f9f9fcb-a99b-41f4-8328-1f29cfb07428)
![17 adding consistency policy back in to my json template](https://github.com/user-attachments/assets/144eeb7e-76f0-4bae-b69b-f873bddf9442)
![18 default consistency eventual](https://github.com/user-attachments/assets/0bc83dd5-3a90-49dd-880e-52cd8f82fb1e)
![1 change session to eventual](https://github.com/user-attachments/assets/4c06fddf-5184-4d04-bc15-771291ad2fd3)


