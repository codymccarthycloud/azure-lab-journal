## Create a Virtual Machine and Connect Using Azure Bastion
Deploy a VM and connect it to Azure Bastion providing secure and seamless RDP/SSH connectivity to your virtual machines, 
directly from the Azure portal without exposing them to the public internet.


## Create a Windows Virtual Machine
In the Azure Portal, click + Create > Virtual Machine.

Fill in the basic details:

Name: vm1
Image: Windows Server 2019 Datacenter - Gen 2
Username: Choose a secure username
Password: Choose a strong password
Under Inbound ports, select None.
Click Next: Disks, then Next: Networking.
In Networking:
Public IP: Select None
NIC Network Security Group: Select None
Click Review + Create and then Create.
Wait for the VM deployment to complete.

## Deploy Azure Bastion
Go to the VM resource once it's deployed.

- Click Connect > Bastion.
- Click Use Bastion.
- Login to the VM using the username and password.

## Connect to the VM Using Bastion

- In the VM resource, click Connect > Bastion.
- Enter the username and password you set during VM creation.
- Click Connect.

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/36827e3a-b6f3-492e-9802-6608bce2bd17)
![2](https://github.com/user-attachments/assets/3ce9b11a-2809-4371-bd67-2b7aaa304d9a)
![3](https://github.com/user-attachments/assets/6b17c2b4-a3fa-4494-bb6c-54f5d19da901)
![4](https://github.com/user-attachments/assets/0eeb5db6-412a-4406-93c1-05405308e155)
![5](https://github.com/user-attachments/assets/8f2067b3-a4b8-410e-a26c-4e7be6396322)
![6](https://github.com/user-attachments/assets/6d8e89f4-448c-4da9-8783-abe476ecef82)
![7](https://github.com/user-attachments/assets/05bd96af-38ba-4c58-867e-add07b457859)
![8](https://github.com/user-attachments/assets/7765c40f-5ee7-4f09-b3c2-b45fcf9ebe95)
![9](https://github.com/user-attachments/assets/39deed43-9581-4a36-8519-6a9f61334a2b)
![10](https://github.com/user-attachments/assets/a3e74039-5312-4702-b468-f3fbf40cfb05)
![11](https://github.com/user-attachments/assets/ae0f9972-9cfe-4e52-94a3-797fd4321f7f)

