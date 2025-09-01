# Archive Cosmos DB Data Using the Change Feed and an Azure Function

**Objective**: Use Azure Functions to archive data from Cosmos DB into Blob Storage using the change feed trigger in Function App.

---


## Verify Lab Environment
- Confirmed the following resources were pre-provisioned:
  - Cosmos DB account with `LabDB` and `LabContainer`
  - Storage account with container `lab-blobs`
  - Log Analytics workspace

## Create Azure Function App
- Searched for **Function App** in the portal and clicked **Create**.
- Configuration:
  - **Resource Group**: Existing lab group
  - **Function App Name**: `mynewaemcfa`
  - **Runtime Stack**: Node.js
  - **Region**: Same as resource group
  - **Plan Type**: Consumption (Serverless)
  - **Storage Account**: Selected existing `labstorage...`
  - **Application Insights**: Enabled
- Clicked **Review + Create**, then **Create**.

## Add Cosmos DB Trigger Function
- Inside the Function App, created a new function using the **Azure Cosmos DB trigger** template.
- Configuration:
  - **Function Name**: `CosmosTrigger1`
  - **Cosmos DB Connection**: Selected existing account
  - **Database Name**: `LabDB`
  - **Container Name**: `LabContainer`
  - **Lease Collection**: Enabled creation
- Created the function and confirmed it appeared in the Function App.

## Add Output Binding to Blob Storage
- Navigated to **Integration** tab.
- Added an output binding:
  - **Type**: Azure Blob Storage
  - **Storage account connection**: (Link storage account)
  - **Parameter Name**: `outputBlob`
  - **Path**: `lab-blobs/{rand-guid}` (Storage Account Container Name)
  

## Test the Function
Used Test/Run with input:

```json
[{"id": "newThing"}]
Verified successful execution in logs.
```

## Update Function Code
- Replaced default code with:
  ```javascript
  module.exports = async function (context, documents) {
    if (!!documents && documents.length > 0) {
      context.log('Document Id: ', documents[0].id);
      context.bindings.outputBlob = documents[0];
    }
  }
  ```
Clicked Save.

## Test/Run 
Used Test/Run with input:

```json
[{"id": "newThing2"}]
Verified successful execution in logs.
```

Checked Blob container lab-blobs — confirmed new blob was created.

## Trigger via Cosmos DB Change Feed
Navigated to Data Explorer in Cosmos DB.

Added new items to LabContainer:

json
{"id": "addeditem"}
{"id": "addeditem2"}
Returned to Blob container and confirmed two new blobs were added.
Opened blob contents to verify document IDs.

## Observations
The change feed reliably triggers the Azure Function on new inserts.
Output binding to Blob Storage works as expected when context.bindings.outputBlob is set.
Function App must be in the same region as Cosmos DB and Storage Account for seamless integration.
Using {rand-guid} in the blob path ensures unique filenames.

## Conclusion
Successfully created and tested an Azure Function triggered by Cosmos DB.
Archived documents to Blob Storage using output bindings.
Validated integration by manually inserting items and verifying blob creation.
**Always confirm binding names and paths match your code.**

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/916d56af-74f8-42e4-92e6-bfa6d0f35a43)
![1a](https://github.com/user-attachments/assets/d8b71c85-f0f7-429b-ae00-e4779e3d8877)
![1aa](https://github.com/user-attachments/assets/3873d9bd-1fe8-48e0-a0ab-608b50ad187c)
![2](https://github.com/user-attachments/assets/d62c0c4e-33df-4eb2-921f-d0b079834d97)
![3](https://github.com/user-attachments/assets/ddadbeb5-3f0b-47d9-a12a-b4874fd97e97)
![4](https://github.com/user-attachments/assets/e7550dff-d196-482a-b40b-9b13a33f0b5d)
![5](https://github.com/user-attachments/assets/7729dff4-9984-4e33-af64-766dde70a6f0)
![6](https://github.com/user-attachments/assets/53286b4b-baa5-4cf6-8970-e44e371bc557)
![7](https://github.com/user-attachments/assets/2d21bacd-c3da-4812-849f-b64a9b5b7a95)
![8](https://github.com/user-attachments/assets/3af71b82-45c4-4435-9738-f31fbd6e8a96)
![9](https://github.com/user-attachments/assets/5feae847-e555-4ed5-ae94-8641d3c22806)
![10](https://github.com/user-attachments/assets/24fd11b9-c4ff-4f50-9bf5-18e0cbc06b39)
![11](https://github.com/user-attachments/assets/0a1415d6-0f5c-4ac4-800d-dc3287f14464)
![12](https://github.com/user-attachments/assets/ea00e980-52d1-44d9-8669-88f7690022fd)
![13](https://github.com/user-attachments/assets/a7a97854-7703-496e-b113-53f4d1b76fbc)
![14](https://github.com/user-attachments/assets/dc970d14-10ed-4720-9387-824cc51c1192)
![15](https://github.com/user-attachments/assets/34f3624e-19dc-410b-9965-6d08f5cc11b3)
![16](https://github.com/user-attachments/assets/bac23f3e-d134-4ea2-b122-79e84ad3046a)
![17](https://github.com/user-attachments/assets/58464cf0-5401-4454-98f2-c9ec6f18d617)
![18](https://github.com/user-attachments/assets/75c1fce7-5261-446c-9d32-1baed0217123)
![19](https://github.com/user-attachments/assets/66c1bfc2-697c-4b23-aceb-51445d9fd1b6)
![20](https://github.com/user-attachments/assets/bb60c9c8-6a50-44f5-9682-aad95cb4ede6)
![21](https://github.com/user-attachments/assets/e6032206-4865-46d5-95c6-cad8cb63462a)
![22](https://github.com/user-attachments/assets/5a203288-bb41-4184-a85e-9c3036536a6e)
![23](https://github.com/user-attachments/assets/9a400a54-11a5-4e6b-8c3d-90aafc26abe4)
![24](https://github.com/user-attachments/assets/a078db66-6ef3-4c86-94e9-e05dd35f1ff2)
![25](https://github.com/user-attachments/assets/6f9bfd04-6a8f-4e65-94c8-b299b0ebf0e5)
![26](https://github.com/user-attachments/assets/16bc86aa-88d3-41b4-90b1-6829a23b0e21)
![27](https://github.com/user-attachments/assets/883dbca8-b2c9-40fa-a68e-1cde58a2c86d)
![28](https://github.com/user-attachments/assets/b345e882-47a3-4497-9121-4afdee7b2fb7)
![29](https://github.com/user-attachments/assets/44fa53d7-92b3-47dd-aba5-96c9a6f5c91f)
![30](https://github.com/user-attachments/assets/06c3b15b-8ba5-47d1-b695-bdcf58a6968b)
![31](https://github.com/user-attachments/assets/e035b215-2b7b-49c7-80d5-378b8336955c)
![32](https://github.com/user-attachments/assets/6c66b067-28a9-4822-b2f7-156da1b1f7b7)
![33](https://github.com/user-attachments/assets/fd03f9af-fe49-4ec5-adcd-e5cdca3779f0)
![34](https://github.com/user-attachments/assets/6dd6ead0-6f76-4201-aa98-830ca0989a49)
![35](https://github.com/user-attachments/assets/d578df1d-2e4a-4650-9e41-ad094ef897e6)

