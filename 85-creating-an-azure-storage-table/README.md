# Creating an Azure Storage Table in Azure Portal


## Create a Storage Account
1. Open the Azure Portal.
2. Click the **menu icon** in the top-left corner.
3. Navigate to **Storage accounts** and click **Add**.
4. Fill in the following:
   - **Resource group**: Select your existing group.
   - **Storage account name**: Must be globally unique.
   - **Location**: Match the resource group’s location.
5. Click **Review + create**, then **Create**.
6. Once deployed, click **Go to resource**.


## Create a Storage Table
1. On the storage account overview page, click **Tables** (or find it in the left-hand menu).
2. Click **+ Table**.
3. Name the table: `training`.
4. Click **OK**.


## Insert Data into the Table
- In the left-hand menu, click **Storage browser**.
- Expand **Tables** and select `actraining`.
- Click **Add entity** and enter:

### Entity 1 (Staff)
- **PartitionKey**: `Staff`
- **RowKey**: `7777`
- **FullName**: `Landon Fowler`
- **FieldOfStudy**: `Databases`

### Entity 2 (Student)
- **PartitionKey**: `Students`
- **RowKey**: `8888`
- **FullName**: `Jesse Hoch`
- **FieldOfStudy**: `Linux`

4. Click **Insert** after each entity.


## Query for Students
1. In the table view, click **Add filter**.
2. Set:
   - **Column**: `PartitionKey`
   - **Value**: `Students`
3. Click **Apply**.
4. You should see only the student entity returned.


## Conclusion
You've successfully:
- Created a storage account
- Created a table
- Inserted entities

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/5ac50c6d-625c-4ed0-b9a6-f5d8b76b9618)
![2](https://github.com/user-attachments/assets/b3557f27-59c7-4dd8-979b-ed7bb7077367)
![3](https://github.com/user-attachments/assets/be360759-721b-4d1e-b3f8-9f22835cff0a)
![4](https://github.com/user-attachments/assets/1a16e59b-d76c-41bb-8d02-189dca6327c2)
![5](https://github.com/user-attachments/assets/12d5702b-665c-488e-8cdb-525c3754750f)
![6](https://github.com/user-attachments/assets/a523aabe-0ec9-4747-ba9d-4a7953ac1d02)
![7](https://github.com/user-attachments/assets/0e0d3bc4-12aa-4c89-a30a-35122ea99a6d)
![8](https://github.com/user-attachments/assets/bb148970-8d95-4073-bb6c-8156c1a04d90)
![9](https://github.com/user-attachments/assets/e6a8ec3a-cba1-41de-a0a3-bbd1e096f8ec)
![10](https://github.com/user-attachments/assets/a99da895-1964-4eb4-a1c4-6c2a37e04887)
![11](https://github.com/user-attachments/assets/c0923d35-8ddd-4b83-8089-9cfc7e31989b)
![12](https://github.com/user-attachments/assets/1ec153dd-0a02-4c02-9869-3ba4b9e9b0f4)
![13](https://github.com/user-attachments/assets/07e21172-2217-4a69-bc72-5bcb769fc401)
![14](https://github.com/user-attachments/assets/1388835a-8984-406f-9abc-eddd4de3418c)


- Queried data using filters

Azure Table Storage is a powerful NoSQL solution for structured data. Great job!
