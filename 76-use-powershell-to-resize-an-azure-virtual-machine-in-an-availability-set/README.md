# Use PowerShell to Resize an Azure Virtual Machine in an Availability Set

## Launch Azure Cloud Shell

## Retrieve VM Details
Get VM object:
```powershell
$vm = Get-AzVM -ResourceGroupName "418-37f7310c-use-powershell-to-resize-an-azure-vir" -VMName "labVM0"
```
Check current size:
```powershell
$vm.HardwareProfile.VmSize
```
## Resize VM to Lower-Cost SKU
Assign new size:
```powershell
$vm.HardwareProfile.VmSize = "Standard_B1s"
```

## Apply the change
```powershell
Update-AzVM -VM $vm -ResourceGroupName "418-37f7310c-use-powershell-to-resize-an-azure-vir"
```
Note: VM must be deallocated before resizing. If the CLI hangs, run Stop-AzVM first.

## Verify Resize
```powershell
Get-AzVM -ResourceGroupName "418-37f7310c-use-powershell-to-resize-an-azure-vir" -VMName "labVM0"
```
## Change labVM1 to Standard_B1s

## Conclusion
VM resize succeeded, but VM Agent status showed "Not Ready" post-resize.
Resizing within an Availability Set can trigger backend delays or agent instability.
Successfully resized labVM0 and VM1 to Standard_B1s using PowerShell.
Demonstrated cost optimization via VM SKU reduction.

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/065793a0-dd60-4fd7-aa21-b6a548b249bf)
![2](https://github.com/user-attachments/assets/9472d7f3-a75a-46a4-8ee9-78967f723dbe)
![3](https://github.com/user-attachments/assets/299daf67-bbcd-4666-af90-22a68feab6ba)
![4](https://github.com/user-attachments/assets/9ae2a072-5bf8-4b7b-9b12-e103970a1fbb)
![6](https://github.com/user-attachments/assets/408ae345-47a0-44fe-822a-d3f849923965)
![7](https://github.com/user-attachments/assets/c5862690-ede5-4935-a3e7-62e4792dea49)
![8](https://github.com/user-attachments/assets/c4255f60-ef0c-4eb9-9bca-9b9155ad5e3b)
![9](https://github.com/user-attachments/assets/032fcb74-e5e8-4706-90fa-5e55526efdbd)
![10](https://github.com/user-attachments/assets/525cdabb-0189-4d20-ab33-f6f25efba66d)
![11](https://github.com/user-attachments/assets/9a8bbb23-aa87-45df-a741-1e7fe028c2db)
![12](https://github.com/user-attachments/assets/ad712d0d-0203-4605-9289-eed22aeb4426)
![13](https://github.com/user-attachments/assets/15358b93-0054-45d7-8f60-75d75537467c)
![15](https://github.com/user-attachments/assets/0b85b262-20c4-4a51-b8f6-678eb133293a)
![16](https://github.com/user-attachments/assets/7b9d37cc-9bed-4613-b7d5-2a2cc1afa3c2)
![14](https://github.com/user-attachments/assets/b817d39e-3eab-4026-b155-b138c92aa915)

