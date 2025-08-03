# Managing Elastic Pools and Pooled Databases in Azure

## 1. When to Use Elastic Pools

Elastic Pools let you share a fixed set of resources (DTUs or vCores + storage) across multiple databases. Use them when you have:

- Many databases with unpredictable or varying usage  
- Cost-sensitive workloads where you can aggregate peak demands  
- Scenarios that require isolation between databases but shared compute/storage  

## 2. Create two SQL Databases and an Elastic Pool

1. **SQL elastic pools** > **+ Add**  
2. Fill in:
   - **Subscription & Resource group**  
   - **Elastic pool name** (unique)  
   - **Region**  
   - **Pricing tier**: choose Basic, Standard, or Premium, then set eDTUs or vCores and storage  
3. Click **Review + create** > **Create**

4. On the **Create SQL Database** blade, configure the first database:
   - **Subscription**: select your subscription  
   - **Resource group**: myRG  
   - **Database name**: myDatabase1  
   - **Server**: mySqlServer (your existing logical server)  
   - Under **Compute + storage**, click **Configure database**, choose **Use existing elastic pool**, pick **myElasticPool**, then **Apply**  

5. Click **Review + create** > **Create**  


### 2.1 Azure CLI (optional)

```bash
# Create resource group if needed
az group create --name myRG --location eastus2
```

```bash
az sql server create \
  --name test-wus-server-01 \
  --resource-group myRG \
  --location eastus2 \
  --admin-user sqladminuser \
  --admin-password YourStr0ngP@ssw0rd!
```

```bash
# Open your client IP in the server firewall
az sql server firewall-rule create \
  --resource-group myRG \
  --server test-wus-server-01 \
  --name AllowMyIP \
  --start-ip-address $(curl -s ifconfig.me) \
  --end-ip-address $(curl -s ifconfig.me)
```

```bash
# Create elastic pool
az sql elastic-pool create \
  --resource-group myRG \
  --server test-wus-server-01 \
  --name myElasticPool \
  --edition Basic \
  --dtu 50 \
  --database-dtu-max 20 \
  --database-dtu-min 0 \
  --storage 4997MB
```

```bash
# Create the first database in the pool
az sql db create \
  --resource-group myRG \
  --server test-wus-server-01 \
  --name test-wus-db-01 \
  --edition Basic \
  --size 100MB \ 
  --elastic-pool myElasticPool

# Create the second database in the pool
az sql db create \
  --resource-group myRG \
  --server test-wus-server-01 \
  --name test-wus-db-02 \
  --edition Basic \
  --size 100MB
  --elastic-pool myElasticPool
```

### Detach Databases and Delete the Pool

- Detach via CLI (optional):

```bash
az sql db update \
  --resource-group myRG \
  --server mySqlServer \
  --name myDatabase1 \
  --elastic-pool ""
```

### Delete Pool CLI (optional):

```bash
az sql elastic-pool delete \
  --resource-group myRG \
  --server mySqlServer \
  --name myElasticPool \
  --yes
```

### 3. Best Practices

Tag all resources (Environment, Application, CostCenter)

Right-size pool based on peak utilization and number of databases
Use auto-pause or auto-scale scripts for vCore pools to optimize cost
Monitor daily and set alerts to avoid hitting pool limits
Align database min/max DTU settings to prevent any one DB from starving others

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/c781c545-5dc4-46dc-951f-a01bb581ac97)
![2](https://github.com/user-attachments/assets/c056ed0a-6f6b-47f5-ab29-c4c87b07f538)
![3](https://github.com/user-attachments/assets/5b1a4c90-1705-4972-868f-5a80709f316a)
![4](https://github.com/user-attachments/assets/6897f840-aef0-47f4-965c-fda2ec7f7c62)
![6](https://github.com/user-attachments/assets/e7517a86-61e6-4345-bf46-2358dc65a58e)
![5](https://github.com/user-attachments/assets/2b53351c-4cfd-4ab6-af08-586b73d6540f)
![7](https://github.com/user-attachments/assets/a6c5bea6-9da6-4a9e-83c0-ddf010c09f3f)
![8](https://github.com/user-attachments/assets/d22c5a5c-6eca-49ad-8143-24882fd659f9)
![9](https://github.com/user-attachments/assets/c3a943fe-9809-4b76-93cf-d518069632f1)
![10](https://github.com/user-attachments/assets/a8e904f0-01db-468e-a1f7-8bc0334023c9)
![11](https://github.com/user-attachments/assets/e78c02e5-bf23-46c7-8dd4-b703124eee1c)
![12](https://github.com/user-attachments/assets/e88f3564-e536-4fba-9fc1-812e33f06398)
![13](https://github.com/user-attachments/assets/9eabd351-1605-4825-9cf7-31437c9a1720)
![14](https://github.com/user-attachments/assets/27dc8eaa-2eff-4030-bcfe-dd9fb70e3fc1)
![15](https://github.com/user-attachments/assets/a44dc707-2f5d-42fe-9da2-f92a7038715c)
![16](https://github.com/user-attachments/assets/c888f354-f0fe-495c-8561-7507d4762390)
