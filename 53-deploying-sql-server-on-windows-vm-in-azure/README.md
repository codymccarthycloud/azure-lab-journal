# Deploying SQL Server on Windows VM in Azure

## Step-by-Step Deployment
1. Search for Azure SQL
In the top search bar, type "Azure SQL"

- Select Azure SQL under Services

2. Create SQL Virtual Machine
- Click Create Azure SQL resource

Under SQL virtual machines, choose:
- Image: Free SQL Server License: SQL 2025 Developer on Windows Server 2025
- Click Create

4. Configure VM Settings
- Resource Group: Select the one created by the lab
- VM Name: Choose a unique name
- Region: (US) West US
- Size: Select B2s, then click Select
- Admin Credentials: Provide username and password
- Public Inbound Ports: Select None

5. Review and Deploy
- Click Review + create
- Validate settings
- Click Create

## Post-Deployment
- Click Go to resource
- You now have a fully functional SQL Server VM
- You can:
- RDP into the VM for local management
- Configure remote access for external clients

### Enterprise vs. Standard Azure SQL VM Server Deployment

In most production cloud environments, especially for enterprise-grade workloads, you'd be using:

Enterprise Edition for:

- High availability (Always On)
- Real-time analytics
- Large-scale transactional systems
- Advanced security and compliance

Standard Edition for:

- Cost-effective deployments
- Smaller apps or internal tools
- Dev/test environments

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/971a15e2-166c-43a7-950d-f9c055d6dd17)
![2](https://github.com/user-attachments/assets/527f92b4-1408-497e-9b7a-1244d56abda8)
![3](https://github.com/user-attachments/assets/6b87973c-ae83-4e79-b3a8-31a782921e9c)
![4](https://github.com/user-attachments/assets/e2ea3814-62e3-4a91-a830-224197700d03)
![5](https://github.com/user-attachments/assets/099bdceb-a7bc-4de0-9e4e-c72e82a6a188)
![6](https://github.com/user-attachments/assets/2f2f01fe-6267-4bea-abe8-d54241663154)
![7](https://github.com/user-attachments/assets/baf6fdbd-ce3c-46aa-b9b0-67d441d57e30)
![8](https://github.com/user-attachments/assets/090838d7-9484-49e5-9cf9-75504c1b0a8b)
![9](https://github.com/user-attachments/assets/cddf942b-6d7d-4f79-83b8-b8df5aad82d3)
