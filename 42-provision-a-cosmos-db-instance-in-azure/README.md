# Provision a Cosmos DB Instance in Azure

This lab walks through creating a Cosmos DB account using the NoSQL API, 
adding a database and container, and configuring settings to stay within the Free Tier limits.

---

## Step 1: Create a Cosmos DB Account

1. Search for **Azure Cosmos DB** and click **+ Create**
2. Fill in the following:
   - **API**: NoSQL
   - **Account Name**: `test-scus-cosmosdb-nosql`
   - **Location**: South Central US
   - **Capacity Mode**: Provisioned throughput
   - **Apply Free Tier Discount**: No

4. Click **Review + Create**, then **Create**

---

## Step 2: Create a Database and Container

>  Free Tier accounts are limited to **1000 RU/s**. To avoid errors, use **manual throughput** set to **400 RU/s**.

1. Navigate to your Cosmos DB account
2. Click **Data Explorer**
3. Click **+ Add Container**
4. Configure the following:
   - **Database Name**: `ToDoList`
   - **Container Name**: `Items`
   - **Partition Key**: `/id`
   - **Throughput**: Manual, set to **400 RU/s**
   - **Indexing Policy**: Set to **None**

5. Click **OK**

---

## Step 3: Optional Configuration

- **Consistency Level**: Eventual
- **Geo-Replication**: Add South Central US if required
- **Notebook Support**: May be disabled in Free Tier

---

## Step 4: Create Container via Azure CLI (Optional)

If the portal blocks container creation due to RU/s limits, use this CLI command:

```bash
az cosmosdb sql container create \
  --account-name test-scus-cosmosdb-nosql \
  --database-name ToDoList \
  --name Items \
  --partition-key-path "/id" \
  --throughput 400 \
  --idx-policy '{
    "indexingMode": "none"
  }'
```

### NOSQL API > Scale & Settings > Indexing Policy > 
{
"IndexingMode":"none"
}

### Create Alert

---

## Lab Output Screenshots

![1 create azure cosmos db](https://github.com/user-attachments/assets/144d688a-d4c7-48bc-b2bf-2db04d6f8d3a)
![2 create cosmos db for nosql](https://github.com/user-attachments/assets/185cd3ea-5b00-4cb1-aaf2-6f1d6916e359)
![3 cosmos db replicate data globally](https://github.com/user-attachments/assets/ba5bdb9a-85bf-4f14-9922-35b5d1d4b9f5)
![4 replicate data globally](https://github.com/user-attachments/assets/09687da2-8d21-40b6-9146-bc987bf67bcf)
![5 default consistency type least expensive will read differently across regions strong is the same](https://github.com/user-attachments/assets/baf224da-9e3c-476e-a1b6-c2f2389382eb)
![6 create quickstart container](https://github.com/user-attachments/assets/cfbf1a29-1d97-428a-a63f-192048d7985b)
![7 alert is set](https://github.com/user-attachments/assets/eab4a4c7-293a-4317-b939-9f12f201346f)
![8 create alert ru;e](https://github.com/user-attachments/assets/ea34650d-30bb-46c5-97cd-b993ff818f31)

