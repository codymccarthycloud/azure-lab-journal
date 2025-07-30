# Azure Policy and Resource Locks Lab Guide

## Azure Policy Overview

Azure Policy helps enforce organizational standards and assess compliance across your resources.

### Steps:
1. **Explore Built-in Policies:**
   - Navigate to **Definitions**
   - Browse built-in policies by category (e.g. Security, Networking, Storage)

2. **Review Custom Policy Interface:**
   - Click **+ Policy definition**
   - Input settings:
     - Name
     - Description
     - Policy rule (JSON format)

## Resource Locks Overview

Locks help protect critical resources from accidental deletion or modification.

### Types of Locks:
- **Delete Lock**: Prevents resource deletion
- **Read-only Lock**: Prevents any changes, including configuration updates

## Applying Locks

### On Web App
1. Navigate to the Web App resource
2. In the left pane, select **Locks**
3. Click **+ Add**
   - **Name**: `prod-webapp-dlock`
   - **Type**: `Delete`
   - **Notes**: Prevent deletion during deployment cycles

### On VM (`lab-VM`)
1. Go to the **lab-VM** resource in Azure
2. Select **Locks** in the left menu
3. Click **+ Add**
   - **Name**: `prod-labvm-rlock`
   - **Type**: `Read-only`
   - **Notes**: Prevent configuration changes; critical for baseline integrity

## Lab Summary
| Task                              | Status    |
|-----------------------------------|-----------|
| Accessed Azure Policy             | Completed |
| Viewed Built-in Policy            | Completed |
| Explored custom policy interface  | Completed |
| Applied Delete Lock on Web App    | Completed |
| Applied Read-only Lock on VM      | Completed |

### Insights
- Delete Lock will prevent the Web App from being deleted
- Read-only Lock will prevent the VM from being modified

---

## Lab Output Screenshots

![1 explore azure policy and resource locks](https://github.com/user-attachments/assets/16a79b71-7951-4539-849e-7b185ec8a12b)
![2 azure policy](https://github.com/user-attachments/assets/acebfb63-b5ba-405c-8ae5-8222b7920f5a)
![3 compliance](https://github.com/user-attachments/assets/5943ad61-3620-423a-aeda-4ae41f1dd580)
![3 remediation](https://github.com/user-attachments/assets/5ddb526c-af5d-46ee-8133-71c1b9396e85)
![4 events state changes](https://github.com/user-attachments/assets/813d1d9d-d03d-4c6d-ae4e-403745fe2e3e)
![5 policy definition](https://github.com/user-attachments/assets/b7d4fa99-28e3-4b87-a6dd-d2064f98b3b8)
![6 add policy definition](https://github.com/user-attachments/assets/61976d46-fbbc-4201-96b8-65ae371ab690)
![7 definitions brought together for a specific purpose initiative](https://github.com/user-attachments/assets/22335b88-be23-4a17-ad32-3e8216a39674)
![8 assignments](https://github.com/user-attachments/assets/d4db5650-6e19-458c-bf3e-2162c10e7d64)
![9 policy exemptions](https://github.com/user-attachments/assets/f723c970-3ce5-4f82-8aec-bdfd2f6cb37e)
![10 navigate to subscriptions](https://github.com/user-attachments/assets/103f1db9-d716-4fb8-a075-3c9b7e62e0d0)
![11 subscriptions resources](https://github.com/user-attachments/assets/706376b6-08d0-4da5-9722-b56984861b6d)
![12 resource locks](https://github.com/user-attachments/assets/f91c2d1b-20d5-48d0-ad24-f95873110897)
![13 subscription resource groups settings locks](https://github.com/user-attachments/assets/a95d923f-b25d-4aa6-9156-75680a5a78d8)
![14 add lock](https://github.com/user-attachments/assets/14ef087b-afdb-49d3-82f3-c87a72019462)
![15 subscription resource group web app apply delete lock](https://github.com/user-attachments/assets/9cc1d547-886b-4dce-8f32-7260feee236c)
![16 lock prevents deleting of the web app but you can modify it](https://github.com/user-attachments/assets/07403635-705d-4d9e-9914-2be24be96ac9)
![17 lab vm create read only lock so it cannot be modified](https://github.com/user-attachments/assets/5a9ea3ea-58fa-44f3-8480-b630bb2689e8)
![18 create a read lock for the vm so it cannot be modified](https://github.com/user-attachments/assets/a931958a-bb7d-4abe-8577-0464db81a3ae)
