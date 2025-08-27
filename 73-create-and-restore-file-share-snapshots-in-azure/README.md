# Create and Restore File Share Snapshots in Azure

## Create a Storage Account and File Share

In Azure Portal:
1. Go to "Storage Accounts" > Create new
2. Choose a resource group and name (e.g., sa402)
3. Select region, performance, and replication options
4. Once created, go to "File shares" > + File share
5. Name it (e.g., fileshare402) and set quota

## Connect File Share to Windows VM
Disable firewall (for lab purposes only)
Connect fileshare through winvm's powershell:
```powershell
$connectTestResult = Test-NetConnection -ComputerName sa402.file.core.windows.net -Port 445
if ($connectTestResult.TcpTestSucceeded) {
    # Save the password so the drive will persist on reboot
    cmd.exe /C "cmdkey /add:`"sa402.file.core.windows.net`" /user:`"localhost\sa402`" /pass:`"D07tmIJ+1i3nmgthnJaAL4G+QqzIgPYiKK6CSbvX5xbRvFCb7Ar4WbyYd95JSDqHPyNRnh593fpN+AStmDTQwA==`""
    # Mount the drive
    New-PSDrive -Name Z -PSProvider FileSystem -Root "\\sa402.file.core.windows.net\fileshare402" -Persist
} else {
    Write-Error -Message "Unable to reach the Azure storage account via port 445. Check to make sure your organization or ISP is not blocking port 445, or use Azure P2S VPN, Azure S2S VPN, or Express Route to tunnel SMB traffic over a different port."
}
```

## Create and Modify a File in the fileshare 
home>create new>text
# In the mounted drive (Z:), create a file:
test.txt

Add initial content:
hello hello

Save and modify it later:
Take a Snapshot
1. Go to your file share
2. Click "Snapshots" tab
3. Select "Take Snapshot"

## Edit file in wimvm fileshare folder
- Edit and save the fileshare .txt

## Restore from Snapshot
1. Go to "Snapshots" tab
2. Browse snapshot contents
3. Locate original version of test.txt
4. Use Restore in the menu option

### Verification
Open the restored test.txt
Confirm it contains the original content: "This is the original version."

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/13e4bb04-6963-4256-94b6-e477c4c6e65a)
![2](https://github.com/user-attachments/assets/c7f03e07-f6a2-45a3-b1ef-3d82b0724d98)
![3](https://github.com/user-attachments/assets/51121357-f733-424c-abd6-1cbf911278ce)
![4](https://github.com/user-attachments/assets/8adfb760-e73d-4279-a1b6-a73acb4d4253)
![5](https://github.com/user-attachments/assets/c1d8afdb-5535-41b4-9eb7-91242eb18a35)
![6](https://github.com/user-attachments/assets/3fe8bdde-4eca-4376-a730-e42174d6bde7)
![7](https://github.com/user-attachments/assets/3cd1b75b-9e3a-4300-8a83-52026b86c2a5)
![8](https://github.com/user-attachments/assets/7c7590ef-1316-4237-bf46-27cd90869521)
![9](https://github.com/user-attachments/assets/274211d7-3cce-4a12-8880-a4182a0e5bae)
![10](https://github.com/user-attachments/assets/1d8c71b4-d9d7-47ed-bacf-1ad39e3ef5db)
![11](https://github.com/user-attachments/assets/b04eeee4-2f7e-4864-8be7-772dc6a5a47e)
![12](https://github.com/user-attachments/assets/32b29466-3302-4ee6-80dc-5f788f61801d)
![13](https://github.com/user-attachments/assets/c806c13e-be78-4ed3-b133-a9ba57727173)
![14](https://github.com/user-attachments/assets/4292c9bd-7900-48c7-b431-f8f1a4875333)
![15](https://github.com/user-attachments/assets/67824caa-101c-4e0d-b1de-362536292d76)
![16](https://github.com/user-attachments/assets/3dfba1b3-b400-4a13-a064-ed421a175476)
![17](https://github.com/user-attachments/assets/4081bb65-e060-4670-8881-763bf646c333)
![18](https://github.com/user-attachments/assets/a7a2b737-39cd-45df-b535-3a72505ee0e6)
![19](https://github.com/user-attachments/assets/69721aaa-ed1e-489f-88a3-5fc9baafdebe)
![20](https://github.com/user-attachments/assets/3ece0bda-e3fe-4821-83d2-4269a98b3ba7)
![21](https://github.com/user-attachments/assets/d0064a63-29b9-4d9c-85d1-7dd54d42c60f)
![22](https://github.com/user-attachments/assets/99fe1d89-2f6b-4acb-8117-d3ac7603cab2)
![23](https://github.com/user-attachments/assets/6d5fa3ec-cf77-4a16-9aeb-7a4079c4928b)
