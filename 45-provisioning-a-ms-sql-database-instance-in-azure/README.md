# Provisioning an MS SQL Database Instance in Azure


Provision an Azure SQL Server with administrator credentials
Deploy a new SQL Database with a chosen performance tier

## 1. Create a SQL Database and server using the GUI

- Navigate to the SQL Database 
- Under the Data Management tab select replicas 
- Create new Geo Replica 
- Assign Replica to new Region
- Ensure Data Ecryption is enabled
- Dynamic Data Masking will allow you to mask data such as email addresses when being viewed
- Add email address masking rule

---

## 2. Deploy an Azure SQL Server using CLI Powershell
Azure SQL Server is a logical container for databases and security policies. You must supply administrator credentials as a PSCredential or via CLI flags.

2.1 PowerShell: Interactive Prompt
```powershell
New-AzSqlServer \
  -ResourceGroupName "myResourceGroup" \
  -ServerName "my-sql-server" \
  -Location "southcentralus" \
  -SqlAdministratorCredentials (Get-Credential -Message "Enter SQL admin credentials")
```

When you run this, you’ll be prompted for:

User: e.g., sqladminuser
Password: e.g., ComplexP@ssw0rd

---

## 3. Deploy a SQL Database
Choose a performance tier by specifying --edition/-RequestedServiceObjectiveName.

```powershell

New-AzSqlDatabase \
  -ResourceGroupName "myResourceGroup" \
  -ServerName "my-sql-server" \
  -DatabaseName "myDatabase" \
  -Edition "Standard" \
  -MaxSizeBytes "53687091200" \
  -RequestedServiceObjectiveName "S0"
```

---

## Lab Output Screenshots


![1 configure powershell and create a storage account create sql database](https://github.com/user-attachments/assets/bf5e282b-a96a-4bca-8eae-3805573e706f)
![2 create a server inside the sql db creation](https://github.com/user-attachments/assets/f06d0ac3-827f-4a4a-a46d-d8c90d57dd55)
![2 create sql database](https://github.com/user-attachments/assets/274dfad5-7f90-4560-995c-3aa05d0ebd38)
![3 sql databases configure compute storage standard](https://github.com/user-attachments/assets/b936b20c-e5a9-456b-90ec-bc5a3d41b69b)
![4 use existing data sample](https://github.com/user-attachments/assets/8328876a-dae3-45f8-b8f6-9c7843e41714)
![5](https://github.com/user-attachments/assets/c26f94bd-99c9-4363-9319-b2fc1107cc5c)
![6 create geo replica in data managment](https://github.com/user-attachments/assets/54339ffe-0e8b-4fda-92f8-57cfdbc71431)
![7 data encryption on](https://github.com/user-attachments/assets/edfb58e8-317b-4687-b7ac-6758812c96af)
![8 dynamic data masking](https://github.com/user-attachments/assets/4f45967f-9782-4ed5-b02b-babe47f5dbe3)
![9 add masking rule](https://github.com/user-attachments/assets/2bdb4c1d-a35f-49a6-b63a-638ddc1e379e)
![10](https://github.com/user-attachments/assets/9b376262-297a-4a8d-8e7b-b5e8e3b037c1)
![11 get credential message enter sql admin credentials](https://github.com/user-attachments/assets/c017f515-f018-4df4-93d5-afb00880dd30)
![12 new azsqldatabase](https://github.com/user-attachments/assets/7274bf16-5ca6-4579-a354-7d381d79e297)
![13 database and server created](https://github.com/user-attachments/assets/1a4f2c35-a960-4a1e-97e4-174e4e3bd5eb)




