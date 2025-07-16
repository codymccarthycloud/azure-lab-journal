#  Lab: Create a Virtual Network in Azure Using Azure CLI

This repository documents the **"Create a Virtual Network in Azure Using Azure CLI"** lab from *A Cloud Guru on Pluralsight*, including additional steps taken to correct region mismatch and showcase deeper CLI proficiency.

---

## Lab Overview

- Mounted a storage account in Azure Cloud Shell
- Identified default region mismatch between storage and deployed resources
- Set the CLI default location manually to "westus"
- Verified new default with "az configure --list-defaults"
- Created a Virtual Network explicitly in West US
- Added two distinct subnets to the VNet for extended practice

---

## Prerequisites

- Azure subscription with appropriate permissions
- Access to Azure Cloud Shell (Bash or PowerShell)
- Existing resource group (e.g. "rg-vnet-lab")   

---

## 1. Mounting Cloud Shell Storage

- Even though the storage account was mounted successfully, the UI did **not** prompt for region selection. The storage account was confirmed to be in **West US** using:

```bash
```

---

## 2. VNet Deployment

**Initial VNet Creation (Default to East US)**  

```bash
# (az network vnet create --name vnet1 --resource-group rg-vnet-lab --address-prefixes 10.1.0.0/16)
```

---

## 3. Default Location Fix

**Set CLI default to West US**

```bash
# (az configure --defaults location=westus)
```

**Confirm the change**

```bash
# (az configure --list-defaults)
```

---

## 4. Redeploy Virtual Network in West US

After setting "westus" as our CLI default, we recreate the VNet to ensure it lands in the correct region:

**VNet Creation (Default to West US)**

```bash
# (az network vnet create --name vnetwest --resource-group rg-vnet-lab --address-prefixes 10.1.0.0/16)
```

---

## 5. Subnet Enhancements

- By creating two individual subnets on different IPs it demonstrates awareness of the task and knowledge to deploy more subnets on the same VNet

**Subnet Enhancements**

```bash
az network vnet subnet create --vnet-name vnetwest --name subnet1 --resource-group rg-vnet-lab --address-prefixes 10.1.1.0/24
az network vnet subnet create --vnet-name vnetwest --name subnet2 --resource-group rg-vnet-lab --address-prefixes 10.1.2.0/24
```

---

## Conclusion

- This lab highlights how implicit region defaults can lead to unexpected deployments. By explicitly configuring Azure CLI defaults and specifying resource locations, you gain precise control over where resources are created. 
  
- Adding multiple subnets demonstrates forward thinking, proactively developing deeper proficiency in network design and CLI usage.

---
 
## What’s Next

Explore Virtual Network Peering to connect VNets across regions

Implement Network Security Groups (NSGs) for granular traffic control

Automate deployments with Bicep or ARM templates

Integrate Azure Firewall or third-party NVAs for advanced network security

---

## Lab Output Screenshots

![mounting storage account to azure CLI](https://github.com/user-attachments/assets/57322b34-3520-4762-bd2f-9f7167699ead)
![bash configuation mount storage account](https://github.com/user-attachments/assets/255c1cf5-f3b4-4477-be23-dfe76343e62d)
![az network vnet create -h -- finding help for vnet creation using CLI](https://github.com/user-attachments/assets/ba67a70c-dbf5-445c-806e-d403ec4ffca4)
![creating vnet1 and changing the default location for vnetwest then creating two subnets on different IPs](https://github.com/user-attachments/assets/143e0c3e-ff6d-4057-8fdf-d75806fadbe0)
![creating additional subnets on the same vnet-- az configure default location-view location](https://github.com/user-attachments/assets/5d74b070-5274-49d4-8e12-f97701545f3f)
