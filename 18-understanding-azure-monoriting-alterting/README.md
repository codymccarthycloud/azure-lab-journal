# Understanding Azure Monitoring & Alerting

---

## 1. Lab Objectives

- Explore Azure Monitor Alert components 
- Create a Metrics alert rule on a storage accounts availability
- Create the Availability Alert Rule
- Create an Action Group


# Storage Account Availability Alert – Azure Portal UI Guide

This document walks through creating an availability alert on a storage account, configuring a multi‐channel action group, and suppressing notifications every Sunday from 03:00 to 05:00—all via the Azure Portal UI.

---

## 2. Create the Availability Alert Rule

1. In **Monitor**, go to **Alerts** > **Alert rules** > **+ Create** > **Alert rule**.  
2. Under **Scope**, click **Select resource**, filter by type **Storage accounts**, and choose your storage account (e.g., `stgmonitorlab`).  
3. Under **Condition**, click **Add condition** and select **Availability** (Min).  
   - Operator: **Less than**  
   - Threshold value: **100**  
   - Aggregation granularity: **Minimum over 5 minutes**  
   - Frequency of evaluation: **1 minute**  
4. Under **Actions**, click **Select action group** and choose `ag-storage-alert`.  

### Create an Action Group

Sign in to the Azure Portal (https://portal.azure.com).  
In the left menu, select **Monitor**.  
Under **Alerts**, click **Manage actions** > **Action groups**.  
Click **+ Create action group**.  
Fill in the basics:
   - Subscription and Resource group  
   - Action group name: `ag-storage-alert`  
   - Display name: `StorageAlerts`  

Under **Notifications**, add:
   - **Email/SMS/Push/Voice**  
     - Email: user@example.com  
  
   - **Webhook**  
     - Name: `webhookAction`  
     - URL: `https://example.com/webhook`  
Review and click **Create**.


5. Under **Alert rule details**:
   - Alert rule name: `alert-storage-availability`  
   - Severity: **Sev error** (or as appropriate)  
   - Description: “Fires when storage account availability drops below 100%.”  
6. Click **Review + create**, then **Create**.

---

## 3. Suppress Notifications During Maintenance Windows

1. In **Monitor**, go to **Alerts** > **Alert processing rules** > **+ Add processing rule**.  
2. Basics:
   - Name: `pr-sunday-maint-suppression`  
   - Scope: Click **Select alert rules**, filter to `alert-storage-availability`, and add it.  
3. Under **Actions**, choose **Suppress notifications**.  
4. Under **Schedule**, set:
   - Recurrence: **Weekly**  
   - Days of week: **Sunday**  
   - Start time: **03:00**  
   - End time: **05:00**  
5. Click **Create**.

---

## Lab Output Screenshots

![1 create action group in alter for storage account](https://github.com/user-attachments/assets/8d4e663c-7be5-4a13-9d05-d7dc6d11e8e8)
![2 create alert rule](https://github.com/user-attachments/assets/33006c81-e397-4775-a75a-ad8fafddc443)
![3 create processing rule select a scope virtual machine   alter rule storage account](https://github.com/user-attachments/assets/1df20101-035c-42eb-b015-3cb9299da741)
![4 creating alter processing rule scheduling](https://github.com/user-attachments/assets/30eeee9b-61d9-4844-bb6b-198b0f7d6c3d)
![5 alert processing rule details](https://github.com/user-attachments/assets/6f588596-9a97-43a1-854b-3b75618f581b)
![6 review create alert processing rule](https://github.com/user-attachments/assets/3dada518-6801-4097-af2b-1b537021d154)



