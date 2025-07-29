# Perform 10 SQL Queries Using Azure Data Studio

## Lab Overview
This guide walks through connecting to Azure SQL from Azure Data Studio, configuring firewall rules, and executing 10 SQL tasks documented in the Pluralsight lab: [Use Azure Data Studio to Perform 10 Fundamental SQL Queries in Azure](https://app.pluralsight.com/hands-on/labs/575abd96-7611-4727-a509-1a9a0f93eb26?ilx=true).

---

## Step 1: Configure SQL Database Firewall

1. Go to [Azure Portal](https://portal.azure.com)
2. Navigate to your SQL Server: `acsql-r236`
3. Open the **Networking** blade
4. Add your **Client IPv4 Address** to the allowed firewall rules
5. Set **“Allow Azure Services and resources to access this server”** to **Yes**
6. Test connectivity in the built-in Query Editor using:
   - **Username:** `LabAdmin`
   - **Password:** `Lab!Pwd9`

---

## Step 2: Retrieve Connection Information

- Copy the **Fully Qualified Domain Name (FQDN)** from the SQL Server Overview page
- Paste into a Notepad for reference: 
Example: acsql-r236.database.windows.net

---

## Step 3: Azure Data Studio Setup

1. Launch **Azure Data Studio**
2. Add your Azure account (`cloud_user_p_...`)
3. Go to **Connections** > **New Connection**
4. Paste the **FQDN** as Server Name
5. Enter credentials:
 - **Username:** LabAdmin
 - **Password:** Lab!Pwd9
6. Connect to the database: `SQL_Lab`
7. Navigate to **Explorer Blade > Databases > SQL_Lab**

---

## Step 4: Run 10 SQL Tasks

Example:
### DML Task 1 — Simple SELECT on View
```sql
SELECT ProductCategoryName, ProductCategoryID, ParentProductCategoryName
FROM vGetAllCategories;
--OUTCOME #1: 37 rows, unordered
```

### Blade Folder Alterations

-Navigate to the Explorer Blade in ADS:
-Expand SQL_Lab database
-Check changes reflected in Tables > SalesLT > SpecialWidgets

Refresh to see:
- Column updates after DDL tasks
- Row changes after DML tasks

## Lab Output Screenshots

![1 navigate to sql database and go to networking firewall rules add your client ip addresses all azure services and resources to access this server](https://github.com/user-attachments/assets/ef0162cd-7e62-4975-a6d4-e9a2041bdcb9)
![2 login to query editor in the SQL database](https://github.com/user-attachments/assets/a85c4627-bc78-49e7-906c-a81d4dfdf245)
![6 SQL DB server connect to azure data studio](https://github.com/user-attachments/assets/6a11bba8-1f49-491c-9e31-d8e126930928)
![4 azure data studio add account grabbing subscriptions from azure](https://github.com/user-attachments/assets/7258feaa-d409-4416-95e3-5ea9e9415397)
![1 download, install, run azure data studio](https://github.com/user-attachments/assets/7063f5f2-bf1c-43c0-92d5-a689bfbeeac5)
![3 azure data studio connection blade azure add account copy the server nsame from the sql database in azure](https://github.com/user-attachments/assets/a22a47a7-59df-4320-bad8-a0d2de2ca3cf)
![5 logged in the azure data studio](https://github.com/user-attachments/assets/f38d7934-de8c-4338-8281-278b8695b5ec)
![6 azure data studio server connect](https://github.com/user-attachments/assets/41fcf41e-e651-4ce8-a1d1-5353d46cedf1)
![7 azure subscription logged in and server connected](https://github.com/user-attachments/assets/0939e422-7960-44df-856c-ae52bc804079)
![8 navigate to databases SQL_Lab right click SalesLT_address and it will provide you with the most recent 1000](https://github.com/user-attachments/assets/2a628109-b8fa-48ea-a43e-ebf7122e410f)

---

![azure data studio query 1](https://github.com/user-attachments/assets/b12220ef-27c9-4793-b9b7-7b35b972edb8)
![azure data studio query 2](https://github.com/user-attachments/assets/c235e970-3c03-414a-b673-211351e78a63)
![azure data studio query 3](https://github.com/user-attachments/assets/89f593af-f58b-4b09-bb0f-cd96e516ab8e)
![azure data studio query 4](https://github.com/user-attachments/assets/63c79736-4404-47d2-8e8c-700de33ad32c)
![azure data studio query 5](https://github.com/user-attachments/assets/abee14af-5a1e-43e2-99db-c1acc61c091d)
![azure data studio query 6](https://github.com/user-attachments/assets/7b10ee08-d0e1-4bac-8d05-78f4dcc97cb2)
![azure data studio query 7](https://github.com/user-attachments/assets/a79739ed-7b9b-4277-bbbf-498fcf487390)
![azure data studio query 8](https://github.com/user-attachments/assets/eb17e758-596a-431a-aeff-947f074ab9f4)
![azure data studio query 9](https://github.com/user-attachments/assets/5ade9c18-e626-4560-95c5-17114111ff4b)
![azure data studio query 10](https://github.com/user-attachments/assets/24e2e615-eaef-4d20-9670-72002bcfc209)

