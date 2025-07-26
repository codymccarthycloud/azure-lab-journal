# Organizing Azure Resources Lab 

## Lab Overview
This hands-on lab guides you through deploying and organizing Azure resources using the **Azure portal** and **Cloud Shell**. Tasks include creating a virtual machine, setting up storage accounts, nesting management groups, and building a resource dashboard.

---

## Objectives
-  Deploy an Ubuntu VM with trusted launch security
-  Create two storage accounts with LRS redundancy
-  Structure resources using nested management groups
-  Build and share a custom dashboard showing storage and VM metrics
-  Use Azure Cloud Shell commands for deployment

---

## Resource Deployment

### Virtual Machine

**Deployed using the dashboard** 

Alternative deployment method:

```bash
az vm create \
  --resource-group <RESOURCE_GROUP_NAME> \
  --name testscusvmjump01 \
  --image UbuntuLTS \
  --size B1s \
  --admin-username cloud_user \
  --admin-password "Go-2-the-Cloud!" \
  --security-type TrustedLaunch  
  --storage-sku StandardSSD_LRS  
  
```

---

### Storage Account

```bash
az storage account create \
  --name pslabhtgswa<RANDOM_NUM> \
  --resource-group <RESOURCE_GROUP_NAME> \
  --location <LOCATION> \
  --sku Standard_LRS \
  --kind StorageV2
```

---

## Resource Organization

- Create top-level management groups: `MG1` and `MG2`
- Nest a child group inside one: `MG1a` or `MG2b`
- Assign your subscription to the correct group if permissions allow

---

## Dashboard Features

Include visual tiles for the following metrics:
- **Storage Capacity Used** (Avg Used Capacity)
- **Disk Transactions** (Sum Transactions)
- **VM CPU Usage** (% CPU)
- **VM Network Traffic** (Inbound/Outbound)
- **VM Available Memory** (Avg Available Memory)


---

## Lab Output Screenshots

![1 create a virtual machine](https://github.com/user-attachments/assets/fc8129a2-5a3b-4efb-83ba-6eef474784ec)
![2 create storage account scus was full deployed to eus](https://github.com/user-attachments/assets/95f34ecd-7ac0-4190-8893-3dbbd850d7a0)
![3 azure cli bash create a storage account](https://github.com/user-attachments/assets/5554e082-7fa1-414d-98dc-ecd77f0eb6f1)
![4 create management groups create nested management group](https://github.com/user-attachments/assets/4856f62b-9c93-4a3e-80d8-a95c28a3c57b)
![5 Dashboard metrics set saved shared](https://github.com/user-attachments/assets/7b6c569b-eded-42ab-b8df-a55a0a2bfa3d)
![6 Resource Monitor](https://github.com/user-attachments/assets/9ee37c75-9750-4768-9d1d-127524b8bb1d)


