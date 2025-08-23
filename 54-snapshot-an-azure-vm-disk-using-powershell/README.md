# Snapshot an Azure VM Disk using PowerShell

Create a snapshot of a virtual machine disk and copying it to an Azure Storage Container using PowerShell.

### Learning Objectives
- Stop and deallocate a VM
- Grant read access to the VM disk
- Copy the disk snapshot to blob storage using AzCopy and PowerShell

## Prepare Variables
```powershell
$rg = "<RESOURCE_GROUP_NAME>"
$vmName = "winVM"
$diskName = "<VIRTUAL_MACHINE_DISK_NAME>"
$sasExpiryDuration = "3600"
$storageAccountName = "<STORAGE_ACCOUNT_NAME>"
$storageAccountKey = "<KEY1_STORAGE_ACCOUNT_KEY>"
$storageContainerName = "container1"
$destinationVHDFileName = "disk1.vhd"
$useAzCopy = 1
```

## Stop the Virtual Machine
```powershell
Stop-AzVM -ResourceGroupName $rg -Name $vmName
```

## Grant Access to the Disk
```powershell
$sas = Grant-AzDiskAccess `
  -ResourceGroupName $rg `
  -DiskName $diskName `
  -DurationInSecond $sasExpiryDuration `
  -Access Read
```

## Create Storage Context
```powershell
$destinationContext = New-AzStorageContext `
  -StorageAccountName $storageAccountName `
  -StorageAccountKey $storageAccountKey
```

## Copy Snapshot to Blob Storage
AzCopy
```powershell
$containerSASURI = New-AzStorageContainerSASToken `
  -Context $destinationContext `
  -ExpiryTime (Get-Date).AddSeconds($sasExpiryDuration) `
  -FullUri `
  -Name $storageContainerName `
  -Permission rw

azcopy copy $sas.AccessSAS $containerSASURI
Option B: Using PowerShell Blob Copy
powershell
Start-AzStorageBlobCopy `
  -AbsoluteUri $sas.AccessSAS `
  -DestContainer $storageContainerName `
  -DestContext $destinationContext `
  -DestBlob $destinationVHDFileName
```

### Completion
Once the snapshot is copied, you’ll see the .vhd file appear in container1 within your storage account. 
This snapshot can be used for backup, migration, or restoration.

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/c866a6a7-60bd-4513-8baf-9908c235a03f)
![2](https://github.com/user-attachments/assets/174fdcb9-53e7-49a5-a09b-98d4640c09df)
![3](https://github.com/user-attachments/assets/4ed54565-ab03-45c2-a5df-85dd594762d0)
![4](https://github.com/user-attachments/assets/b140dae9-b00a-46a1-9b6e-7520b964c255)
![5](https://github.com/user-attachments/assets/e0099480-ed00-433b-807f-238fe8d630b7)
![6](https://github.com/user-attachments/assets/014bc5b2-4d4d-466d-aca9-94d8b4621371)
![9](https://github.com/user-attachments/assets/d37a0ff2-c044-4349-806d-d8e26fb0256f)
![10](https://github.com/user-attachments/assets/956bb5cc-baa5-4c5f-b98c-76c0f3745438)
![11](https://github.com/user-attachments/assets/ee411ffa-7677-4bc1-8312-b5dc2f44f2af)
![12](https://github.com/user-attachments/assets/a59bf52f-e205-438b-a6ec-007b174bb561)
![13](https://github.com/user-attachments/assets/df825e8a-a501-4b64-b22f-e38316bcce59)




