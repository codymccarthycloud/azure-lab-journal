# Shred JSON in Azure with Synapse Analytics

## Create Synapse Workspace
Search for Synapse Analytics
Click Create Synapse workspace

Fill in:
Resource group: Use provided one
Workspace name: *unique name*
Region: West US
Account name: *unique name*

File system name: Create new
Set SQL Server admin login and password
Click through Networking, Tags, and Review + create
After deployment, open Synapse Studio

## Create Dedicated SQL Pool
In Synapse Studio, go to Manage > SQL pools
Click + New
Name: *unique name* 
Performance level: DW100c
Click Create

## Create and Populate Table
Create Table
```sql
CREATE TABLE piestore1(
  id INT NULL,
  name VARCHAR(255) NULL,
  price VARCHAR(255) NULL,
  sweet VARCHAR(255) NULL
)
```
### Populate Table with JSON
```sql
DECLARE @json NVARCHAR(4000) = N'{ 
    "pies" : {
            "sweet" : [
            { "id" : 1, "name" : "Cherry", "price" : "3.50" },
            { "id" : 2, "name" : "Chocolate", "price" : "4.99" },
            { "id" : 3, "name" : "Pumpkin", "price" : "4.00" }
        ],
            "savory" : [
            { "name" : "Meat", "price" : "6.00" },
            { "name" : "Chicken", "price" : "5.00" },
            { "name" : "Veggie", "price" : "4.00" }
        ]
    }
}';

INSERT into piestore1
SELECT *
FROM OPENJSON(@json, '$.pies.sweet')
WITH (
    int INT '$.id',
    name VARCHAR(255) '$.name',
    price VARCHAR(255) '$.price',
    sweet NVARCHAR(max) '$' AS JSON
)

```
## Shred JSON
Parse JSON from Column
```sql
SELECT * FROM OPENJSON((SELECT sweet FROM piestore1 WHERE id = 1))
```
### Result
You’ll see the nested JSON parsed into a readable table format—this is JSON shredding in action.

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/155bead1-4498-46b5-ba85-aa75e9abac85)
![2](https://github.com/user-attachments/assets/c49d0805-03ef-4df0-9557-e6ed5d9c88e5)
![3](https://github.com/user-attachments/assets/e3a8e4cf-93e7-4aa9-9fde-3af69e2b3ce0)
![4](https://github.com/user-attachments/assets/c20e00a6-dc29-45ba-bbf3-1b73aeebad88)
![5](https://github.com/user-attachments/assets/92fe1ccf-35e4-46a0-baf8-2257ccdb5761)
![6](https://github.com/user-attachments/assets/5f96b72e-0e1f-4914-a676-9a339a245903)
![7](https://github.com/user-attachments/assets/0e37e247-2092-4a91-bf4d-e0bc853148bd)
![8](https://github.com/user-attachments/assets/a963b145-4fa2-46d1-a3ee-fa934b6fd758)
![9](https://github.com/user-attachments/assets/16cdcaf9-b3a9-4377-9f4d-53b3eecc0370)
![10](https://github.com/user-attachments/assets/d8e04da4-e26d-4ff5-bb08-72afc786084a)
![11](https://github.com/user-attachments/assets/476846aa-0e9e-4eed-8ef7-fa8e2cc6dc9e)
![12](https://github.com/user-attachments/assets/999f7cdd-bcdc-46d3-879f-7e8c7da2d606)
![13](https://github.com/user-attachments/assets/2827fc95-4fba-4fcc-99b6-d945482e7fcd)
![14](https://github.com/user-attachments/assets/4e9c2dbc-ac52-429a-af5f-a3bfb075a8a0)
![15](https://github.com/user-attachments/assets/c92a3b11-eb2e-4c99-afb7-9948112b8c96)
![16](https://github.com/user-attachments/assets/648da2c8-f3fc-43ae-886b-2486636a44f9)
![17](https://github.com/user-attachments/assets/42962d9b-c64f-41da-905b-5a30a4fe0762)
![18](https://github.com/user-attachments/assets/8693e834-34f5-4dd5-9b85-cb5e70d722d2)
![19](https://github.com/user-attachments/assets/cfdc01fd-048a-4e50-a3ff-d98d88a0d629)
