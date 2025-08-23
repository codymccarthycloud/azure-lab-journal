# Survey Resource Alerts Using Azure Monitor

This guide walks you through surveying deployed resources and any warnings, advisories, or errors using Azure Monitor. 
You’ll explore various monitoring blades, activate Application Insights on an App Service, and complete the lab.

## Prerequisites

- Access to the Azure portal in an incognito/private window.
- Lab Azure subscription and resource group pre-provisioned for this exercise.
- Lab credentials provided on the Hands-on Lab page (username and password).

## Learning Objectives

- Identify all deployed resources and any warnings, advisories, or errors
- Access the Azure Monitor interface
- Examine these monitoring panes:
- Applications
- Virtual Machines
- Storage Accounts
- Containers
- Networks (and verify settings)
- Inspect the deployed App Service (webxxxxxxx) and activate Application Insights

## Open Azure Monitor

1. In the portal search bar, type “Monitor” and select Azure Monitor.

In the left-hand menu under Insights, you’ll find dedicated blades for each resource type.

2. Examine the Applications Pane
Under Insights, click Applications.

Review any alerts or health advisories for deployed Application Insights resources.

3. Examine the Virtual Machines Pane
Under Insights, click Virtual Machines.

Verify VM health, CPU/memory utilization, and any active alerts.

4. Examine the Storage Accounts Pane
Under Insights, click Storage accounts.

Check for performance metrics, capacity warnings, and alert rules.

5. Examine the Containers Pane
Under Insights, click Containers.

Review container health, resource usage, and any critical alerts.

6. Examine the Networks Pane
Under Insights, click Networks.

Verify network security group (NSG) and firewall settings; note any blocked or denied traffic events.

## Inspect the App Service & Activate Application Insights

- In the portal, navigate to your App Service named webxxxxxxx.
- In its left menu, expand Settings → Monitoring and select Application Insights.
- Click “Turn on Application Insights”, choose to Create a new resource, and Save.
- Wait for the provisioning to complete, then switch to the Live Metrics or Logs view to confirm telemetry flow.
- Confirm that you’ve surveyed all resource alerts and activated Application Insights.

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/5b08cebd-e0c7-4217-88c6-dfffbd4acc94)
![2](https://github.com/user-attachments/assets/62b201b1-4ad1-4c98-b3cc-9a1cedf3c9a6)
![3](https://github.com/user-attachments/assets/5a5e2a97-db63-4fac-9a0e-a1fd2ea65e77)
![4](https://github.com/user-attachments/assets/3bd8cef0-ad11-4169-9fa9-f1b4b31dfc60)
![3a](https://github.com/user-attachments/assets/b11dbb84-4018-4e96-9801-7f9dec84c326)
![5](https://github.com/user-attachments/assets/a06632ff-d56f-475e-ba05-683f63af2ab1)
![6](https://github.com/user-attachments/assets/318db174-cd97-4577-a656-04fd8ee20e2c)
![7](https://github.com/user-attachments/assets/bc0ed7ca-7ea6-4b7b-9fb3-f0890357f089)
![8](https://github.com/user-attachments/assets/62323279-5de0-4b00-9eba-ba527a97d0b7)
![15](https://github.com/user-attachments/assets/cfc375ca-b0c1-42a0-8d79-3f576bb41ed5)
![9](https://github.com/user-attachments/assets/157f1c26-bfcc-478d-b7df-12b780eab5c5)
![10](https://github.com/user-attachments/assets/0f2dd63e-0bef-4bf2-aa7d-c81f5b421d9e)
![11](https://github.com/user-attachments/assets/e11eec5c-9bae-4328-8c2b-5d8e767eed91)
![12](https://github.com/user-attachments/assets/9c7a397f-5523-4da8-a1f3-5ad74fda0fbf)
![13](https://github.com/user-attachments/assets/02db95a9-249d-41fc-b584-f759a987bd96)
![14](https://github.com/user-attachments/assets/16d06701-4be9-4e28-a8bc-232e391a06f2)
