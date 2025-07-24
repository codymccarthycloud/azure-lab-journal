# Lab: Deploying an Azure VM with Terraform

---

## Step 1: Create and Upload the Terraform File

1. Upload the provided Terraform `.tf` configuration code into Azure Bash.
2. Modify the following line with your lab’s resource group name:
```hcl
   resource_group_name = "187-c756d714-deploying-an-azure-vm-with-terraform"
```

---

## Step 2: Deploy the VM Using Terraform CLI

```bash
terraform init
terraform plan
terraform apply
```
## Step 2: Deploy the VM Using Terraform CLI

In Azure Cloud Shell (Bash), run the following commands:

terraform init
terraform plan
terraform apply

- Confirm deployment by typing "yes" when prompted.
- Terraform will provision the following:
  - Virtual Network (VNet)
  - Subnet
  - Public IP
  - Network Interface (NIC)
  - Boot Diagnostics Storage Account
  - Virtual Machine (Ubuntu)

---

## Step 3: Validate Deployment in Azure Portal

- Go to the Azure Portal → Resource Group → VNet
- Confirm the **Subnet** was created under the VNet
- Go to **Network Interface (`robot-nic`)** → IP Configurations:
  - Private IP assigned (e.g., 10.0.0.4)
  - Public IP assigned
  - NIC connected to correct Subnet

---

## Step 4: Confirm VM Boot via Serial Console

- Navigate to the deployed VM → **Serial Console**
- Confirm console output shows Ubuntu login screen or diagnostics prompt
- VM status should display **Running**
- Optional: Check Boot Diagnostics tab for screenshots and log files stored in the associated storage account

---

## Conclusion

Terraform successfully deployed and configured:
- VM with public/private IPs
- Subnet within VNet
- Network Interface with IP configuration
- Boot diagnostics via linked storage account

Deployment confirmed via CLI and Portal  
Serial Console verifies successful boot  
Lab completed with clean infrastructure state
Learn to create .tf file deployments that work across multiple cloud platforms

---

## Lab Output Screenshots

![test vm tf](https://github.com/user-attachments/assets/fb5451fc-3576-45d9-bf68-9ae472419609)
![confirming the subnet has been added to the VNET](https://github.com/user-attachments/assets/dec0a331-1551-428d-a994-169d7b824519)
![private and public ip assigned to the NIC network interface](https://github.com/user-attachments/assets/d893cadd-fa5d-42a8-8e53-a6a2d593244a)
![vm serial console check if it is running](https://github.com/user-attachments/assets/e75b16c3-f961-4dd2-b118-b35849379111)
