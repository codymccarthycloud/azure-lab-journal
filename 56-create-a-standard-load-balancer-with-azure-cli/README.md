# Create a Standard Load Balancer with Azure CLI

## Lab Overview
This lab walks you through deploying a Standard Load Balancer in Azure using the CLI. You'll create two virtual machines, configure a load balancer with health probes and rules, and verify connectivity using a public IP.

---

## Prerequisites
- Azure subscription access
- Azure CLI installed or access to Azure Cloud Shell
- Resource group created (e.g., `MyResourceGroup`)
- Bash terminal preferred

---

## Set Resource Variables in Cloud Shell

```powershell
$RG = az group list --query '[].name' -o tsv
$LOC = az group list --query [].location -o tsv
$NSG = az network nsg list --query [].name -o tsv 
$VNET = az network vnet lsit --query [].name -o tsv 
$SNET = az network vnet list --query [].subnets[0].name -o tsv
```

## Create Two NICs for VMs

```powershell
az network nic create \
  --resource-group MyResourceGroup \
  --name MyNic1 \
  --vnet-name MyVNet \
  --subnet MySubnet

az network nic create \
  --resource-group MyResourceGroup \
  --name MyNic2 \
  --vnet-name MyVNet \
  --subnet MySubnet
```

## Prepare cloud-init Configuration

Create a file named `cloud-init.txt` with the following content:

```powershell
vim cloud-init.txt
```
Enter the following into the file:

```powershell
#cloud-config
package_upgrade: true
packages:
  - nginx
  - nodejs
  - npm
write_files:
  - owner: www-data:www-data
  - path: /etc/nginx/sites-available/default
    content: |
      server {
        listen 80;
        location / {
          proxy_pass http://localhost:3000;
          proxy_http_version 1.1;
          proxy_set_header Upgrade $http_upgrade;
          proxy_set_header Connection keep-alive;
          proxy_set_header Host $host;
          proxy_cache_bypass $http_upgrade;
        }
      }
  - owner: azureuser:azureuser
  - path: /home/azureuser/myapp/index.js
    content: |
      var express = require('express')
      var app = express()
      var os = require('os');
      app.get('/', function (req, res) {
        res.send('Hello World from host ' + os.hostname() + '!')
      })
      app.listen(3000, function () {
        console.log('Hello world app listening on port 3000!')
      })
runcmd:
  - service nginx restart
  - cd "/home/azureuser/myapp"
  - npm init -y
  - npm install express@4.16.4 -y
  - nodejs index.js
```

Type ':wq' to quit after using ESC to exit Insert mode. 
w = write (save)
q = quit

## Create Virtual Machines
Use a cloud-init file or basic VM creation:

```powershell
az vm create \
  --resource-group MyResourceGroup \
  --name MyVM1 \
  --nics MyNic1 \
  --image debian11 \
  --admin-username azureuser \
  --generate-ssh-keys \
  --custom-data cloud-init.txt
Repeat for VM2 with a second NIC.
```

```powershell
az vm create \
  --resource-group MyResourceGroup \
  --name MyVM2 \
  --nics MyNic2 \
  --image debian11 \
  --admin-username azureuser \
  --generate-ssh-keys \
  --custom-data cloud-init.txt
Repeat for VM2 with a second NIC.
```

## Create the Load Balancer

Create the load balancers public ip:
```powershell
az network public-ip create \
  --resource-group MyResourceGroup \
  --name MyPublicIP \
  --sku Standard
```

Create the load balancer:
```powershell
az network lb create \
  --resource-group MyResourceGroup \
  --name MyLoadBalancer \
  --sku Standard \
  --frontend-ip-name MyFrontEnd \
  --backend-pool-name MyBackEndPool \
  --public-ip-address MyPublicIP
```

Create a Health Probe:
```powershell
az network lb probe create \
  --resource-group MyResourceGroup \
  --lb-name MyLoadBalancer \
  --name MyHealthProbe \
  --protocol Http \
  --port 80 \
  --path /
```

## Create a Load Balancing Rules
```powershell
az network lb rule create \
  --resource-group MyResourceGroup \
  --lb-name MyLoadBalancer \
  --name MyHTTPRule \
  --protocol Tcp \
  --frontend-port 80 \
  --backend-port 80 \
  --frontend-ip-name MyFrontEnd \
  --backend-pool-name MyBackEndPool \
  --probe-name MyHealthProbe
```

## Attach NICs to Backend Pool
Repeat for each VM:

Add the first VM to the load balancer pool:
```powershell
az network nic ip-config address-pool add `
--address-pool myBackEndPool `
--ip-config-name ipconfig1 `
--nic-name myNicVM1 `
--resource-group $RG `
--lb-name myLoadBalancer
```

Add the second VM to the load balancer pool:
```powershell
az network nic ip-config address-pool add `
--address-pool myBackEndPool `
--ip-config-name ipconfig1 `
--nic-name myNicVM2 `
--resource-group $RG `
--lb-name myLoadBalancer
```

Set variable for NIC:
$NIC = "nic1-07f2p"
Using the VM that came with the lab with a preconfigured NIC.

```powershell
az network nic ip-config address-pool add \
  --address-pool MyBackEndPool \
  --ip-config-name ipconfig1 \
  --nic-name $NIC \
  --resource-group $RG \
  --lb-name myLoadBalancer
```

## Test Load Balancer Connectivity
Get the public IP:

```powershell
az network public-ip show \
  --resource-group $RG \
  --name MyPublicIP \
  --query ipAddress \
  --output tsv
```

Paste the IP into your web browser. You should see alternating responses from VM1 and VM2 (e.g., “Hello World from host VM1/2”).

---

### Lab Objectives Recap:

- Set Resource Variables in Cloud Shell
- Create Two Network Interfaces for VMs
- Create a cloud-init File
- Create two virtual machines
- Create a Standard Load Balancer
- Configure NICs and attach to backend pool
- Add health probe and load balancing rule
- Verify cconnectivity via public IP

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/13cc140b-b406-4124-85f6-dab8c5bb8671)
![2](https://github.com/user-attachments/assets/dffa2af0-028b-4311-bf2a-61092fbff7b5)
![3](https://github.com/user-attachments/assets/0dfbafb4-5cad-4ecc-bee7-d180f14ca37b)
![4](https://github.com/user-attachments/assets/c5552b3a-7de1-4ee1-8726-5a78619a2d95)
![5](https://github.com/user-attachments/assets/c0592f1d-25f2-45a0-a5bc-945935bf7def)
![6](https://github.com/user-attachments/assets/7da78115-f404-4aca-b015-69b3dca3e99f)
![8](https://github.com/user-attachments/assets/8f7d7c56-c5c6-426f-8806-575b24ef78f5)
![9](https://github.com/user-attachments/assets/14d0fc43-5a95-4e24-bd41-1ee355c49d12)
![7](https://github.com/user-attachments/assets/32c20e8a-e5e2-413a-aba6-d8cead8c0fc7)
![10](https://github.com/user-attachments/assets/35b879d1-cf14-41e6-9692-f2de7bf21400)
![11](https://github.com/user-attachments/assets/a66947f7-5544-45f9-9758-67bca286c71a)
![12](https://github.com/user-attachments/assets/6b284a77-0f5b-4bb7-aebf-324ab893841f)
![13](https://github.com/user-attachments/assets/fd6494a5-4e1c-4726-9c6d-d222e9a89a7d)
![14](https://github.com/user-attachments/assets/b1a467d7-80d5-4a48-8db2-9c1df0930e21)
![15](https://github.com/user-attachments/assets/ac3ca3fc-ad33-4372-97cd-cc64c93b38ff)
![16](https://github.com/user-attachments/assets/8fe2eb4d-8858-4c80-a936-017315f46d61)
![17](https://github.com/user-attachments/assets/be73e46c-4eda-4a3e-870e-95ea396cd2f9)
![18](https://github.com/user-attachments/assets/81103a0c-c4ce-493d-bb92-a88d23caeaea)
![19](https://github.com/user-attachments/assets/edf55649-e12a-473e-b194-104cd8dc5b7a)
![20](https://github.com/user-attachments/assets/603cd222-bb44-491f-9211-9385bf19a8f4)
![21](https://github.com/user-attachments/assets/24c867f4-32c9-4bf2-bce7-ce446cf520de)
![22](https://github.com/user-attachments/assets/05d2fe96-3411-41ee-b6a7-1f79032dd882)
![23](https://github.com/user-attachments/assets/307eab41-7ee5-4d9c-98b7-475a9fce2e5f)
![24](https://github.com/user-attachments/assets/7d3a5490-30a1-4573-882b-58f8fcff1d5b)
