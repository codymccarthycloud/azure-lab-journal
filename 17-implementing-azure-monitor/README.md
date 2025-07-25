# Lab 17: Implementing Azure Monitor on SQL Database

## Overview
This lab demonstrates how to provision a SQL database and implement monitoring using Azure Monitor, including security auditing, alerting, diagnostic settings, and log analysis.

---

## 1. Prepare the Environment

### Provision SQL Database
- Region: **West US**
- Performance Tier: **Basic (5 DTU)**, **2 GB** data size
- Enable **Public Endpoint**
  - Add Azure Services & Client IP
- Load **Sample Data**
- Skip Trial Setup

### Provision Log Analytics Workspace
- Region: **West US**
- Link workspace to SQL server for telemetry

---

## 2. Implement Monitoring in SQL Database

### Security Auditing
- Create a new **Storage Account**
- Enable **Auditing** on SQL database
  - Destination: Storage Account
  - Audit Action: All

### Diagnostic Settings
- Send **Errors**, **Timeouts**, and **Basic Metrics** to Log Analytics
```bash
az monitor diagnostic-settings create \
  --name "sqldb-diag" \
  --resource "<SQL_RESOURCE_ID>" \
  --workspace "<LOG_ANALYTICS_ID>" \
  --metrics '[{"category": "AllMetrics", "enabled": true}]' \
  --logs '[{"category": "Errors", "enabled": true}, {"category": "Timeouts", "enabled": true}]'
```
---

# Azure Monitor Lab: SQL Database Monitoring & Auditing

## Objective
Implement Azure Monitor on a SQL Database to track performance, enable auditing, configure alerts, and explore diagnostic logs.

---

## Steps Overview

### Alert Rule: DTU > 70%
- **Condition:** DTU used > 70%
- **Aggregation:** 5-minute average
- **Evaluation Frequency:** 1 minute
- **Threshold Type:** Static
- **Action Group:** Email Notification

---

## Metrics Dashboard
Create charts in Azure Monitor for:
- **Avg DTU Limit**
- **Avg Data Space Used**

> Navigate to: Azure Portal → Monitor → Metrics

---

## Log Activity & Queries

### Sample SQL Queries
```sql
-- Query 1: Join Product Categories
SELECT TOP 20 pc.Name AS CategoryName, p.Name AS ProductName
FROM SalesLT.ProductCategory pc
JOIN SalesLT.Product p ON pc.ProductCategoryID = p.ProductCategoryID;

-- Query 2: Insert Sample Product
INSERT INTO SalesLT.Product (
    Name, ProductNumber, Color, ProductCategoryID, StandardCost, ListPrice, SellStartDate
)
VALUES (
    'myNewProduct', 123456789, 'NewColor', 1, 100, 100, GETDATE()
);
```

### CPU Usage Query
```kusto
AzureMetrics
| where ResourceProvider == "MICROSOFT.SQL"
| where TimeGenerated >= ago(60min)
| where MetricName == "cpu_percent"
| parse _ResourceId with * "/microsoft.sql/servers/" Resource
| summarize avg(Average) by Resource, MetricName
```
---

# 4. Review Audit & Storage Logs

- Check Security Audit Logs
- View .xel files in Azure Storage
- Confirm queries are logged
- Validate Storage Account Logs
- Use Azure Storage Explorer or Portal
- Confirm ingestion of activity data

## 5. Conclusion

- Created a SQL Database Server
- Create Audit Log
- Pin Metric Charts to Test Dashboard
- Set up Alert Rules
- Diagnostic Settings: Send Errors, Timeouts, Basic Metrics to Log Analysis
- Check Logs after Running Scripts in the Query Editor
- Review Audit Records
- Inspect Storage Account Container for the Script Entries Run with Query Editor

---

## Lab Output Screenshots

![create MySQL database server](https://github.com/user-attachments/assets/79ad6004-547c-44a4-9944-a3e8482d6cf5)
![deploy MySQL database server](https://github.com/user-attachments/assets/56440c46-6489-4c88-8070-bc89e6a798ca)
![deployment](https://github.com/user-attachments/assets/b63de4cb-9388-4a1b-80dc-335e957fcb45)
![step 2 create server](https://github.com/user-attachments/assets/383ec5f4-879d-4f4e-a1d4-8bba0720f432)
![step 3 configure service tier basic 2gb](https://github.com/user-attachments/assets/1f650d6d-c8b3-4880-b523-707a12055ac9)
![step 4 networking configure ](https://github.com/user-attachments/assets/f84a9e1f-783a-4111-b6ef-875a182838de)
![step 5 deploy after additional settings data source sample use sample database](https://github.com/user-attachments/assets/508aa787-6eab-4771-82f5-e49a263545a9)
![step 5 create log analytics](https://github.com/user-attachments/assets/a687ce1c-acb6-42c8-b066-812b47036582)
<img width="3820" height="2002" alt="step 6 created resources" src="https://github.com/user-attachments/assets/aa66bfee-a27c-4612-9fbe-5e744fde43be" />
<img width="3838" height="2010" alt="step 7 monoriting alter" src="https://github.com/user-attachments/assets/7fb05606-378e-416e-bd47-43437fa79bea" />
![step 8 alert rule created](https://github.com/user-attachments/assets/4d654581-d5a9-4a94-9e89-3ec7420c7e92)
![step 9 metrics stu limit avg and data space data space used max pin to dashboard](https://github.com/user-attachments/assets/5b680702-20d3-4280-86e9-0941aee341db)
![diagnostic settings](https://github.com/user-attachments/assets/90c7ad6a-c523-4611-b86f-bf056d9f37b6)
![diagnostic settings created](https://github.com/user-attachments/assets/3b9a34e7-23df-4325-abbe-5633998591d1)
![run two querys and go back to monitoring](https://github.com/user-attachments/assets/2688c640-e801-43cf-a198-e4ce3fb44a3c)
![audit records](https://github.com/user-attachments/assets/1c205ae8-0aa7-445c-a7cb-3ad545a49415)
![logging querys creating a trail](https://github.com/user-attachments/assets/0fd7e2e3-72dd-46ad-a50d-f8f36bd843a8)
![storage container holding the records of the query entries](https://github.com/user-attachments/assets/455aef45-05ff-433a-af23-627862a95c7d)
![data from logs enabled through diagnostic settings](https://github.com/user-attachments/assets/d7fd936a-786b-4743-9126-e9b5eff7695d)
![custom dashboard metrics](https://github.com/user-attachments/assets/2f7b4da2-a48c-4094-ad63-25979040711c)

