## Deploying Azure Database for MySQL

---

1. **Create a Resource**
   - Search: `Azure Database for MySQL Flexible Server`
   - Select: *Microsoft-published service*

2. **Basics Tab**
   - Subscription: `Your Azure Subscription`
   - Resource Group: `mysql-flex-lab-rg`
   - Server Name: `codydb-mysql` *(must be globally unique)*
   - Region: `Canada Central`
   - Workload Type: `Development`
   - Database Version: `8.0`

3. **Authentication**
   - Admin Username: `mysqladmin`
   - Admin Password: `StrongPassword!123`

4. **Review + Create**
   - Click `Create` to deploy the server

5. **Connect to MySQL**
   Use tools like MySQL Workbench or the Azure CLI.

-- Lab Output Screenshots

![create MySQL database server](https://github.com/user-attachments/assets/81b19665-50ca-4859-98fe-71c4e1007f10)
![deploy MySQL database server](https://github.com/user-attachments/assets/3a597f84-8625-4218-9153-18c1e28ca50e)
![deployment](https://github.com/user-attachments/assets/26bb53e2-80d2-4fc8-8bfb-68630266b560)

