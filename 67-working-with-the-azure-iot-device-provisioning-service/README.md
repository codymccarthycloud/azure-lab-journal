# Working with the Azure IoT Device Provisioning Service

## Learning Objectives
Solution to monitor park gates connecting IoT hubs with custom permissions to a DPS:
- Use existing resource group and storage account mounted with CLI
- Create an Azure Device Provisioning Service (DPS) using Azure CLI
- Create scoped access policies for secure linking
- Link two IoT Hubs to the DPS
- Configure DPS to assign devices based on lowest latency

## Create Scoped Access Policies in IoT Hubs
For each IoT Hub (iothub-XXXXX and iothub2-XXXXX):
- Go to Shared Access Policies
- Click + Add
- Name: dps

Permissions:
- Registry read
- Registry write
- Service connect
- Click Save

## Create the Device Provisioning Service
In Cloud Shell, run:

```bash
az iot dps create --name IoTDPS-XXXXX --resource-group <TAB> --location westus
```
Replace XXXXX with your lab suffix
Use <TAB> to auto-complete the resource group name

## Link IoT Hubs to DPS
- Go to your DPS resource → Click Linked IoT hubs
- Click + Add
- Select IoT Hub
- Use the dps access policy
- Repeat for the second IoT Hub

## Configure Allocation Policy
- In DPS > Click Manage allocation policy
- Select: Lowest latency (ensures connection to the nearest IoT Hub)
- Click Save

### Conclusion
- Created a DPS instance
- Scoped access securely with custom policies
- Linked multiple IoT Hubs
- Configured device assignment based on latency

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/2db182cc-719d-474d-a8fa-b434a143a88c)
![2](https://github.com/user-attachments/assets/5292c76d-55bf-4e1e-90ee-4e4821309557)
![3](https://github.com/user-attachments/assets/c40f69f2-dc42-4b25-90d4-28f3027009eb)
![4](https://github.com/user-attachments/assets/61180f58-8ca7-4529-9136-951e70212145)
![5](https://github.com/user-attachments/assets/521d1d21-40a0-4bca-8717-2aa01357fece)
![6](https://github.com/user-attachments/assets/8e2a34ba-aea2-4de9-93ba-106972b0921a)
![7](https://github.com/user-attachments/assets/f5101f7d-fd56-4869-adfc-92306b4100bf)
![8](https://github.com/user-attachments/assets/0b6e3d7a-2f6e-4f02-8352-19431f53f3ea)
![9](https://github.com/user-attachments/assets/eb990d2e-42f8-4a88-b74b-54934c1de3ad)
![10](https://github.com/user-attachments/assets/ecd7102e-6a77-441e-a38d-3de09f841bf7)
![11](https://github.com/user-attachments/assets/3a25b773-a540-4a53-afa6-a0f38849d37d)
![12](https://github.com/user-attachments/assets/d0e98516-7387-43d1-801f-04147d507fd5)
![13](https://github.com/user-attachments/assets/8e25ee60-ebdf-4f46-a344-cbf9b725b419)
![14](https://github.com/user-attachments/assets/efd94037-1a0c-46b6-9d6a-0e06bde7c86c)
![15](https://github.com/user-attachments/assets/ea823b42-1fcf-4fd3-ad21-4a40156a7cf7)
![16](https://github.com/user-attachments/assets/f059ffa5-14b8-46d8-8838-db7d0ecbcc71)
![17](https://github.com/user-attachments/assets/9336eafd-170c-475e-b5b5-e9a75161d9e1)
