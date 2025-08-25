# Add Existing Data Disk to a VM in Azure

Decommission a VM in Azure while retaining its data disk, and then attaching that disk to another VM.

### Overview
- Delete WinVM2 but retain its data disk
- Attach the retained disk to WinVM1
- Verify the disk is accessible from WinVM1

## Decommission WinVM2 and Retain the Disk
- Go to the Azure Portal
- Navigate to WinVM2
- Click Delete
- In the deletion prompt, uncheck the box that deletes the associated storage
- Confirm deletion

## Attach Existing Disk to WinVM1
- Go to WinVM1 in the Azure Portal
- Select Disks from the left-hand menu
- Click + Add data disk
- Under Name, select the existing disk from WinVM2
- Save the changes

## Verify Disk on WinVM1

- Connect to WinVM1 via RDP
- Open File Explorer
- Navigate to Disk Management
- Initialize and format the newly attached disk if needed
- Confirm the disk is visible and usable

Always double-check that you're not deleting the disk when removing a VM.
Use tags to track disk origin if managing multiple resources.

### Conclusion
- WinVM2 is deleted
- Its data disk is successfully attached to WinVM1

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/64aa295f-726a-4782-bf45-e43911584fa8)
![2](https://github.com/user-attachments/assets/193f04b1-f190-41c5-a483-b2396219275f)
![3](https://github.com/user-attachments/assets/051b5bae-5ef9-46dc-aae7-0f434c6064e5)
![4](https://github.com/user-attachments/assets/93487642-edc2-4bdb-a28f-7e7de5c4456c)
![5](https://github.com/user-attachments/assets/7c4c1375-f47c-46f6-8e56-c687ec55a6d4)
![6](https://github.com/user-attachments/assets/be06c566-450e-4247-b008-a0af8443bf01)
![7](https://github.com/user-attachments/assets/1d39646e-b0a1-48ba-b720-6845f655113b)
![8](https://github.com/user-attachments/assets/a8dd2b77-51e5-4116-b96a-559f29997f04)
![9](https://github.com/user-attachments/assets/8e44fadf-0472-4fb9-80f9-227c83584c10)
![10](https://github.com/user-attachments/assets/4ca70cf1-d63f-426f-9134-185625ce9cd2)
