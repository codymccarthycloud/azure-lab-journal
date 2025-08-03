# Create a Virtual Machine and Connect to It Using Azure Bastion

## Overview
This lab walks through creating a Windows virtual machine (VM) in Azure and securely connecting to it using Azure Bastion. 
Bastion allows secure RDP/SSH access directly from the Azure portal without exposing your VM to the public internet.

---

## Learning Objectives
- Create a Windows Virtual Machine
- Deploy Azure Bastion
- Connect to the VM using Azure Bastion

---

## Steps

### 1. Create a Windows Virtual Machine

- **VM Name**: `test-eus-vm-01`
- **Image**: Windows Server 2019 Datacenter Gen 2
- **Authentication**: Choose a username and password
- **Networking Configuration**:
  - Public inbound ports: `None`
  - Public IP: `None`
  - NIC Network Security Group: `None`

  This ensures the VM is isolated from public internet access.

---

### 2. Deploy Azure Bastion

- Go to the **Virtual Machine** resource in the Azure portal.
- Click **Connect** > **Bastion**.
- Follow the prompts to deploy Azure Bastion in the same virtual network.

  Bastion requires a subnet named `AzureBastionSubnet` with a minimum of /27 address space.

---

### 3. Connect to the VM Using Azure Bastion

- In the Azure portal, navigate to your VM.
- Click **Connect** > **Bastion**.
- Enter your credentials.
- Click **Connect** to open an in-browser RDP session.

 This method avoids public IP exposure and enhances security.

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/aea62bf1-a389-4a29-bd5d-979aa8376258)
![2](https://github.com/user-attachments/assets/f6f16b13-f5ab-4279-a0ae-d7227f8ad8e6)
![3 connect vm via bastion](https://github.com/user-attachments/assets/38f89848-fa71-4b3b-b357-21dc2f5acb1b)
![4](https://github.com/user-attachments/assets/d4ea04fe-7a13-4f28-a0f5-938998aad16f)
![5](https://github.com/user-attachments/assets/2c3bb5d5-b341-4eae-a057-8958de57dd59)
![6](https://github.com/user-attachments/assets/0baaec46-3001-497a-9df1-74ddfa31d3e3)
![7](https://github.com/user-attachments/assets/ac43876c-c089-4bba-995e-ba2a40ed6ef7)






---

