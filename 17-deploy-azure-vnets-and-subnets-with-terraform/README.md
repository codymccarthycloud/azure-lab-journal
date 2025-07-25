# Deploy Azure VNETs and Subnets with Terraform

## Lab Overview
In this lab you will use Terraform inside Azure Cloud Shell (Bash) to provision:
  - A Resource Group  
  - An Azure Virtual Network (VNet)  
  - Two Subnets within that VNet  

Objective: verify connectivity and inspect your new network topology.

---

## Azure Cloud Shell Setup
1. Open the Azure Portal and click the **Cloud Shell** icon (>_) in the top bar.  
2. Select **Bash** if prompted.  
3. Wait for your storage account and file share to be mounted (this persists your files and state across sessions).

---

## 📄 Create Terraform Configuration

Create a file named `Deploy Vnet and 2 Subnets customize names` with the following content (replace names/locations as needed):

```hcl
terraform {
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "3.0.0"
    }
  }
}

provider "azurerm" {
  features {}
}

resource "azurerm_resource_group" "rg" {
  name     = "rg-terraform-vnet"
  location = "East US"
}

resource "azurerm_virtual_network" "vnet" {
  name                = "vnet-terraform-lab"
  address_space       = ["10.0.0.0/16"]
  location            = azurerm_resource_group.rg.location
  resource_group_name = azurerm_resource_group.rg.name
  tags = {
    Environment = "Lab"
    CreatedBy   = "Admin"
  }
}

resource "azurerm_subnet" "subnet_a" {
  name                 = "subnet-a"
  resource_group_name  = azurerm_resource_group.rg.name
  virtual_network_name = azurerm_virtual_network.vnet.name
  address_prefixes     = ["10.0.1.0/24"]
}

resource "azurerm_subnet" "subnet_b" {
  name                 = "subnet-b"
  resource_group_name  = azurerm_resource_group.rg.name
  virtual_network_name = azurerm_virtual_network.vnet.name
  address_prefixes     = ["10.0.2.0/24"]
}
```

---

## Upload & Deploy
Click the Upload/Download button in Cloud Shell and upload main.tf.

Run:

```bash
terraform init
terraform plan
terraform apply
```

Verify the plan shows creation of VNet, and Subnets: Apply

---

## Verify Deployment

  - In the Azure Portal, go to Resource Groups → rg-terraform-vnet.
  - Under Resources, confirm you see:
  - Virtual network: vnet-terraform-lab
  - Subnets: subnet-a, subnet-b

---

## Lab Output Screenshots

![1 customize tf file with names and resource group](https://github.com/user-attachments/assets/59ed0893-5f9e-4d4b-b471-672668404f69)
![2 correct format after pasting resource group in tf file](https://github.com/user-attachments/assets/dad4a95a-cc23-4cc6-8803-c94bc303018a)
![3 upload tf file to azure cli](https://github.com/user-attachments/assets/34e8da6d-a2e6-4654-a49e-e662c9feb779)
![4 terraform init plan apply vnet and subnets created with custom names](https://github.com/user-attachments/assets/202d9dd7-d93b-4227-83ca-334485f26572)
![5 check vnet settings subnets with custom names running on different ips 3 resources added with tf confirmed](https://github.com/user-attachments/assets/808d543c-8298-4fd5-87b1-7a88809a43c2)








