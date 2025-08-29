# Configure Data Masking in Azure SQL Database

## Create SQL Server and Database

- Go to Azure Portal and click Create
- Search for Azure SQL and select Create
- Under SQL databases, choose Single Database
Set:
  Database name: sampledb1
  Server: Click Create new
  Server name: Unique name (e.g., server1022c9)
  Authentication: SQL authentication
  Admin login: cloud_user
  Password: 97L^Fw*W
- Location: Same as resource group
Under Compute + storage, set:
- Service tier: Standard
- DTUs: 200

Under Networking:
- Connectivity method: Public endpoint
- Add current client IP: Yes
- Under Additional settings:
- Data source: Sample
- Click Review + create, then Create.

## Configure Data Masking
- After deployment, click Go to resource.
- In the left menu, under Security, select Dynamic Data Masking.
- Click Add mask.
Set:
- Schema: SalesLT
- Table: Customer
- Column: EmailAddress
- Masking format: Email (aXXX@XXXX.com)
- Click Add, then Save.

## Create a Non-Admin User
Open Query Editor from the left menu.
Log in using:
- Username: cloud_user
- Password: 97L^Fw*W

Run the following SQL:

```sql
CREATE USER non_admin WITH PASSWORD = '<Lab Password>';
ALTER ROLE db_datareader ADD MEMBER non_admin;
```

## Verify Data Masking
Log out and log back in as:

Login: non_admin
Password: 97L^Fw*W

Run the query:

```sql
SELECT FirstName, LastName, EmailAddress 
FROM [SalesLT].[Customer]
```
### Confirm that EmailAddress values are masked (e.g., aXXX@XXXX.com).

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/201b966a-44cc-4a7a-8ae1-d9db4d90b470)
![2](https://github.com/user-attachments/assets/8de5370e-7d7b-4b35-8b3a-e25a4b085eb6)
![3](https://github.com/user-attachments/assets/f3381547-5fbc-43d8-83a9-a1e37d633422)
![5](https://github.com/user-attachments/assets/7c52a5a3-969a-4130-adf1-474a48f7725d)
![6](https://github.com/user-attachments/assets/488a37fd-d5d1-4797-877e-069b17998ef1)
![7](https://github.com/user-attachments/assets/986abc22-fd20-44f8-aaeb-405fbe1877cf)
![8](https://github.com/user-attachments/assets/9bfde95e-8141-4a84-b0b4-797792eb5683)
![9](https://github.com/user-attachments/assets/297ddda2-8fad-4a78-a1dc-698f90e972cf)
![10](https://github.com/user-attachments/assets/c2b17058-a46d-4a5a-ae3e-f48caccb6aaf)
![12](https://github.com/user-attachments/assets/a173ae92-3e51-456e-a301-69b9c9244b1e)
![13](https://github.com/user-attachments/assets/12a98ea7-959b-4047-b2ab-1a6b2782cadb)
![14](https://github.com/user-attachments/assets/2710cecd-4ca9-4b6a-9683-d75cfba41231)
![4](https://github.com/user-attachments/assets/10fb42a6-a9cc-43bc-b63a-5f2a09a9dd4c)
![11](https://github.com/user-attachments/assets/4370ac2d-8ca4-4373-b371-6a54be44ab6f)
![15](https://github.com/user-attachments/assets/5bfb1c2c-0df2-4760-b3f1-dfcdeb5a8993)
![17](https://github.com/user-attachments/assets/cc0098dd-01e6-4a8a-b089-a0f33e2b6e19)
![16](https://github.com/user-attachments/assets/27da197b-e21b-4ff7-9b71-fd527c240b90)
![18](https://github.com/user-attachments/assets/0a7efd73-de56-42ca-bb6b-105ec29f154d)
