# Azure Lab: Create Multiple Subnets and NSG Seperating Two VMs on the Same VNET


### Subnet Creation Steps
1. Go to Virtual Networks `MyVNet`
2. Click **Settings** > **Subnets** > **Subnet**
3. Name: `Subnet2`
4. Address range: `10.0.1.0/24`
5. Save

---

## Subnet Setup
- Subnet1 (Windows VM):
  - Name: Subnet1
  - Address Range: 10.0.0.0/24
  - Assigned VM IP: 10.0.0.4 (Windows VM)

- Subnet2 (Linux VM):
  - Name: Subnet2
  - Address Range: 10.0.1.0/24
  - Assigned VM IP: 10.0.1.4 (Linux VM)

### Assign linVM to Subnet2
1. Go to **Virtual Machines** → `linVM`
2. Stop the VM
3. Go to **Networking** > **Network Interface**
4. Click on **IP Configurations**
5. Select `ipconfig1`
6. Change **Subnet** to `Subnet2`
7. Optionally assign static IP: `10.0.1.4`
8. Save and start the VM again

---

## Network Security Group Rules

### NSG for Subnet1
- **Outbound Deny Rule**
  - Name: BlockOutboundToSubnet2
  - Destination: 10.0.1.0/24
  - Direction: Outbound
  - Protocol: Any
  - Action: Deny
  - Priority: 100

### NSG for Subnet2
- **Inbound Deny Rule**
  - Name: BlockInboundFromSubnet1
  - Source: 10.0.0.0/24
  - Direction: Inbound
  - Protocol: Any
  - Action: Deny
  - Priority: 101

---

## Verification Steps

- RDP into `winVM` at `10.0.0.4`
- Run: `ping 10.0.1.4`
- Expected Result: **Request timed out** (ICMP blocked by NSG)
- Confirm subnet isolation enforced by NSG rules

---

## Outcome
Successfully demonstrated cross-subnet traffic isolation using NSG rules in Azure. Windows and Linux VMs assigned to separate subnets. Traffic blocked bidirectionally.

---

## Lab Output Screenshots

![adding a subnet2](https://github.com/user-attachments/assets/1855d96b-3caa-43da-9454-38598ff0ce72)
![assigning the linVM NIC ip configuration to subnet2](https://github.com/user-attachments/assets/2f0d0297-378d-4a47-ac48-14b98655c401)
![denying any traffic coming from subnet2 to subnet1](https://github.com/user-attachments/assets/40aaa41f-64c2-40ee-ba0b-6b7792fccbd8)
![denying outbound traffic from subnet1 to subnet2](https://github.com/user-attachments/assets/ded1ac69-8c91-4ba3-b705-3a4768679772)
![download RDP file and open winVM rdp](https://github.com/user-attachments/assets/28fd3d02-df0a-42bc-951b-0307efd702c0)


