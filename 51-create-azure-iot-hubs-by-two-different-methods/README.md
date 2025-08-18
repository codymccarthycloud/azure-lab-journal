# Create Azure IoT Hubs by Two Different Methods

## Method 1: Azure Portal GUI

Steps:

- Log in to the Azure Portal in an incognito browser window.
- Navigate to the resource group overview and note the region.
- Click Create > Search for IoT Hub > Select Create.

Fill in:

- IoT Hub Name: Unique name (e.g., MyHub1)
- Region: Same as resource group
- Connectivity: Public access
- Pricing Tier: S1: Standard
- Units: 1
- Enable Defender for IoT
- Click Review + Create, then Create.
- Wait for deployment and verify the hub in the resource group.

## Method 2: Azure CLI via Cloud Shell

Steps:
- Open Cloud Shell from the Azure Portal (select Bash).
- Configure storage:
- Region: Same as resource group
- Storage Account: Unique lowercase name
- File Share: cloudshell

Run the CLI command:

```bash
az iot hub create --name <UniqueHubName> --resource-group <ResourceGroupName> --sku B1 --unit 1
```


## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/03365840-3352-4d84-a1bd-fd1e43199375)
![2](https://github.com/user-attachments/assets/a36dbe58-c32b-4be5-bdd7-9fca3328e5b8)
![3](https://github.com/user-attachments/assets/787b13df-7c2d-4190-80dd-2752620d4afd)
![5](https://github.com/user-attachments/assets/79aa7e5d-91b2-4fcb-aef2-70e97f980b8b)
![4](https://github.com/user-attachments/assets/1e9646d0-805a-47c3-9031-a980a909e551)
![6](https://github.com/user-attachments/assets/c66457be-638e-4715-a5fc-0b1694e0f4db)
![7](https://github.com/user-attachments/assets/7fb0146e-e0f0-4968-a7ff-88529314fbec)
![8](https://github.com/user-attachments/assets/53a75619-63ee-4e2b-8927-2b572d7de509)
![9](https://github.com/user-attachments/assets/fe280325-e573-48ae-83a0-3ff5e717edd3)
![10](https://github.com/user-attachments/assets/da1f8d51-e08c-4115-8072-6ed926cdb278)

