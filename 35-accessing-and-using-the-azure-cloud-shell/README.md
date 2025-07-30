# Accessing and Using the Azure Cloud Shell

## Learning Objectives

- Configure the Azure Cloud Shell environment
- Execute Azure CLI and PowerShell commands
- Create and remove a virtual machine using both interfaces

---

## Steps Performed

### Configure Cloud Shell

- Click the **Cloud Shell icon** ( >_ ) in the Azure Portal
- Select **PowerShell** when prompted
- In storage options:
  - Click **Show advanced settings**
  - Use the lab-provided **subscription**
  - Choose an **existing resource group**
  - Select **Central US** as the location
  - Create a **new, uniquely named storage account** and **file share**
  - Click **Create storage**

### Azure CLI Usage

Used CLI to list resources:
```bash
az group list
az storage account list
az vm list
az resource list
```

## Create a VM with Azure CLI

```bash
az vm create \
  --resource-group <your-rg> \
  --name testcusvm01 \
  --location centralus \
  --image debian11 \
  --size standard-b1ms \
  --admin-username azureuser \
  --generate-ssh-keys \
  --public-ip-sku standard

```

Confirmed deployment via:

```bash
az vm show --name testcusvm01 --resource-group <your-rg>
```
PowerShell Cmdlets
Used Cloud Shell (PowerShell) to inspect resources:

```bash
Get-AzResourceGroup
Get-AzStorageAccount
Get-AzVM
Get-AzResource
```

Remove VM via PowerShell

```bash
Remove-AzVM \
  -Name testcusvm01 \
  -ResourceGroupName <your-rg>
```

Verified deletion with:

```bash
Get-AzVM -ResourceGroupName <your-rg>
```

### Observations

- Cloud Shell initialized successfully
- Both CLI and PowerShell provided full access to Azure resources
- VM deployment and teardown worked seamlessly in CLI across interfaces

---


## Lab Output Screenshots 

![1 create a sa using powershell azgroup list review the resource group az storage account list](https://github.com/user-attachments/assets/5942606b-f8e2-40ab-8168-51868b89932b)
![2 az vm create powershell cli](https://github.com/user-attachments/assets/2796b31a-6d7a-4453-a646-1c13134c1617)
![3 get azresourcegroup get azvm get azresource pipe ft](https://github.com/user-attachments/assets/920e417a-d682-4a9a-b515-20302443c8a0)
![4 ft file table remove azvm n g using cli](https://github.com/user-attachments/assets/bd2a82e8-1033-4a6b-9e0d-c67df9349cd8)
![5 vm removed using cli](https://github.com/user-attachments/assets/851046cd-c191-4d76-b6b7-c701e4b76a25)






