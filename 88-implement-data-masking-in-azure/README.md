# Implement Data Masking in Azure SQL Database

In this lab, you’ll act as a database owner who configures Dynamic Data Masking (DDM) to protect sensitive data from unauthorized access. 
You’ll create masking rules and simulate access using a test user.

## Access Azure SQL Database
Log into Azure Portal
Navigate to the SQL Database resource
Select Query editor (preview) from the left menu
Authenticate using:
Login: azureadmin
Password: ACloudGuru!

## View Customer Data
Expand the Tables folder
Right-click SalesLT.Customer → Select Top 1000 Rows
Review the unmasked data in the Results pane

## Configure Dynamic Data Masking
In the left menu, go to Security > Dynamic Data Masking
Under Recommended fields to mask, add masks for:
LastName → Default
EmailAddress → Email
AccountNumber → Custom string
Exposed Prefix: 1
Exposed Suffix: 3
Padding String: xxxxx
Click Save to apply masking rules

## Create Test User and Grant Permissions
```sql
-- Create test user
CREATE USER TestUser WITHOUT LOGIN;

-- Grant SELECT permissions
GRANT SELECT ON SalesLT.Customer TO TestUser;
GRANT SELECT ON SalesLT.SalesOrderHeader TO TestUser;
```

## View Masked Data as TestUser
```sql
-- View masked customer data
EXECUTE AS USER = 'TestUser';
SELECT TOP (100) [FirstName], [LastName], [CompanyName], [SalesPerson], [EmailAddress], [Phone]
FROM [SalesLT].[Customer];

-- View masked account number
SELECT AccountNumber FROM [SalesLT].[SalesOrderHeader];
REVERT;
```

## Toggle Masking Permissions
```sql
-- Allow unmasked view
GRANT UNMASK TO TestUser;

-- Revoke unmasked view
REVOKE UNMASK TO TestUser;
```

## View All Masked Columns
```sql
SELECT c.name, tbl.name AS table_name, c.is_masked, c.masking_function
FROM sys.masked_columns AS c
JOIN sys.tables AS tbl ON c.[object_id] = tbl.[object_id]
WHERE is_masked = 1;
## Clean Up
sql
DROP USER TestUser;
```

---

```sql
--You will notice the data is not yet masked
--To view the masked data go to the next step to create a TestUser
SELECT TOP (100) 
[FirstName],
[LastName],
[CompanyName],
[SalesPerson],
[EmailAddress],
[Phone]
FROM [SalesLT].[Customer]

--Create TestUser
CREATE USER TestUser WITHOUT LOGIN

--Grant TestUser the permission to select data on SalesLT.Customer and SalesLT.SalesOrderHeader Tables
GRANT SELECT ON SalesLT.Customer TO TestUser
GRANT SELECT ON SalesLT.SalesOrderHeader TO TestUser


--View the SalesLT.Customer table as TestUser
--Notice LastName and EmailAddress is masked

EXECUTE AS USER = 'TestUser'

SELECT TOP (100) 
[FirstName],
[LastName],
[CompanyName],
[SalesPerson],
[EmailAddress],
[Phone]
FROM [SalesLT].[Customer]


--View the  SalesLT.SalesOrderHeader table as TestUser
--Notice Account Number is Masked

EXECUTE AS USER = 'TestUser'

SELECT 
AccountNumber
FROM [SalesLT].[SalesOrderHeader]

REVERT
GO

--Allow TestUser to view the data unmasked

GRANT UNMASK TO TestUser

--Remove permission to view unmasked data

REVOKE UNMASK TO TestUser; 


--- View all masked columns
SELECT c.name, tbl.name as table_name, c.is_masked, c.masking_function

FROM sys.masked_columns AS c

JOIN sys.tables AS tbl 

 ON c.[object_id] = tbl.[object_id]

WHERE is_masked = 1;

--Clean Up
DROP User TestUser
```

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/5303a3da-4024-4a8f-a520-10fb2420277b)
![2](https://github.com/user-attachments/assets/c9ac9447-e108-4965-b216-ed130bfeaebb)
![3](https://github.com/user-attachments/assets/e41c929b-32ea-436a-8ba6-184e93ac0ab2)
![4](https://github.com/user-attachments/assets/694832ce-d13e-4335-8921-cee0f206b7cb)
![5](https://github.com/user-attachments/assets/bd95ee8f-6680-4bcf-81fd-57650854b9cf)
![6](https://github.com/user-attachments/assets/e8429c65-e815-4094-aa6e-9c0e5b127110)
![7](https://github.com/user-attachments/assets/36c9871e-6172-40d7-b670-f987a8275ea9)
![8](https://github.com/user-attachments/assets/c3573d14-f4d1-416b-98f3-44c04928e61b)
![8a saved](https://github.com/user-attachments/assets/9b4fc2c8-4eee-4b79-8c94-c56fad12c286)
![9](https://github.com/user-attachments/assets/87676327-429e-493a-90fb-af4464f540f3)
![10](https://github.com/user-attachments/assets/9763a3f4-b5f8-4803-98e5-36b0d58c5942)
![11](https://github.com/user-attachments/assets/74a1aa0c-5354-4674-a43e-29a2c1338964)
![12](https://github.com/user-attachments/assets/3a650973-c371-4f2d-8cda-d56815680365)
![13](https://github.com/user-attachments/assets/7dc68ae3-89b8-4240-bb46-7b9e675ba703)
![14](https://github.com/user-attachments/assets/ec943acf-aa74-487c-8636-c1ee217824a6)
![15](https://github.com/user-attachments/assets/b80862a1-23c5-4cb2-a6e0-bd845ee96d62)
![16](https://github.com/user-attachments/assets/834d3a5f-4777-4d4d-b19f-2679b746ac01)
![17](https://github.com/user-attachments/assets/ead9145d-1e1a-486f-81d5-2eea1b538d28)
![18](https://github.com/user-attachments/assets/724f91e2-d11a-4221-843a-ae89783d02fe)
![19](https://github.com/user-attachments/assets/2cf24775-5631-4d8d-abc5-b6a49cb0b7bd)
![20](https://github.com/user-attachments/assets/bdfe2e4c-6d49-4cef-af74-0b3c267401d3)





