# Creating an Azure Storage Account with PowerShell

---

## Step 1: Set Variables
```powershell
# Find your resource group 
Get-AzResourceGroup
# Set your region and resource group name
$location = "westus"                       # Replace with your preferred region
$resourceGroupName = "myResourceGroup"     # Use your actual resource group name
```

---

## Step 2: Create the Storage Account
```powershell
New-AzStorageAccount `
  -ResourceGroupName $resourceGroupName `
  -Name $storageAccountName `
  -Location $location `
  -SkuName "Standard_LRS" `
  -Kind "StorageV2"
```

---

## Lab Output Screenshots

![1 open cloud shell in azure powershell configure use existing storage account](https://github.com/user-attachments/assets/b3844a1f-5cc7-42c2-bb12-08c221fc6de9)
![2 create storage account using pwsh cli](https://github.com/user-attachments/assets/903e6feb-7042-4f9a-8962-575e1aa94374)
