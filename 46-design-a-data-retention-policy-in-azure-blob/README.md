# Azure Blob Storage Data Retention Policy

This policy defines the retention, deletion, and archival requirements for all data stored in Azure Blob Storage. 
It ensures compliance with regulatory mandates, optimizes storage costs, and enforces data integrity through automated lifecycle management and immutability controls.

## 1. Purpose  
To establish consistent, automated processes for retaining, archiving, and deleting blobs in Azure Storage accounts, 
ensuring that data is kept no longer than necessary and remains immutable when required by law or policy.

## 2. Scope  
Applies to all Azure Storage Accounts that host Blob data across all subscriptions and environments 
(Development, Test, Production). Every container, folder, and blob created must conform to this policy.

## 3. Definitions  
  Hot Tier – optimal for frequently accessed data, highest cost per GB, low access latency  
  Cool Tier – for infrequently accessed data, lower storage cost but higher access costs  
  Archive Tier – for rarely accessed data, lowest storage cost, data must be rehydrated before use  
  Time-Based Retention Policy – enforces a minimum retention period during which blobs cannot be modified or deleted  
  Legal Hold – prevents deletion of blobs until the hold is manually removed, irrespective of retention period  
  Lifecycle Management – Azure Blob Storage feature that automates tier transitions and deletes based on rules  

## 4. Implementation in Azure Portal  
1. Navigate to your Storage Account > **Data management** > **Lifecycle Management**.  
2. Click **Add rule**, assign a descriptive name (e.g., “AuditFiles7YearRetention”).  
3. Under **Rule scope**, select “Limit blobs with filters” and define your container path or prefix.  
4. In **Base blobs**, add actions:
   - **Tier to Cool** if last modified > X days  
   - **Tier to Archive** if last modified > Y days  
   - **Delete** if last modified > Z days  
5. Enable **Blob versioning** if historical versions must be retained separately.  
6. Save the policy; Azure evaluates it daily and enforces transitions and deletions automatically.

## 6. Sample JSON for Lifecycle Management  
```json
{
  "rules": [
    {
      "name": "AuditAndCompliance7Year",
      "enabled": true,
      "type": "Lifecycle",
      "definition": {
        "filters": { "prefixMatch": ["audit/"] },
        "actions": {
          "baseBlob": {
            "tierToCool": { "daysAfterModificationGreaterThan": 30 },
            "tierToArchive": { "daysAfterModificationGreaterThan": 365 },
            "delete": { "daysAfterModificationGreaterThan": 2555 }
          }
        }
      }
    },
    {
      "name": "TransactionLogs90Days",
      "enabled": true,
      "type": "Lifecycle",
      "definition": {
        "filters": { "prefixMatch": ["logs/"] },
        "actions": {
          "baseBlob": {
            "tierToCool": { "daysAfterModificationGreaterThan": 30 },
            "delete": { "daysAfterModificationGreaterThan": 90 }
          }
        }
      }
    }
  ]
}
```

---

## 7. Roles and Responsibilities
- Storage Admin – configures lifecycle and immutability policies, reviews exceptions.
- Compliance Officer – defines legal and regulatory retention durations, audits enforcement.
- Application Owners – classify data, specify container paths and prefixes in rules.
- Security Team – monitors policy violations, investigates unauthorized deletions or modifications.

## 8. Monitoring and Reporting
- Enable Storage Analytics Logging and Metrics to track lifecycle actions and immutability violations.
- Use Azure Monitor alerts for rule failures or policy misconfigurations.
- Generate monthly compliance reports showing blob counts per tier, deletion events, and legal hold statuses.

## 9. Exceptions and Change Control
- All requests to shorten or extend retention periods must be submitted in writing to the Compliance Officer. 
- The Storage Admin will implement approved changes and document updates in the policy revision log.

## 10. Review and Revision
- This policy must be reviewed annually or when regulatory requirements change. 
- The Compliance Officer coordinates reviews, and the Storage Admin updates lifecycle and immutability settings accordingly.

---

## Lab Output Screenshots

![1 create storage account](https://github.com/user-attachments/assets/3fea9e43-eb6b-4d80-9c4b-2c223c6dce4a)
![2 create container in the storage account](https://github.com/user-attachments/assets/7ae2222d-d452-4fe7-b8c9-3c9cf15a7326)
![3 save github attributes](https://github.com/user-attachments/assets/2d88771b-e397-4fc2-9f0b-e63063805933)
![4 container github txt file upload](https://github.com/user-attachments/assets/6f531338-1906-4842-947d-0c2c464508f5)
![5 change blob from hot to cool](https://github.com/user-attachments/assets/cab7bd88-e743-40d6-b5e3-a650f344339b)
![6 lifecycle management](https://github.com/user-attachments/assets/bb1a4230-2766-4d54-88e5-3320e197f5a0)
![7 Add Rule Lifecycle Management](https://github.com/user-attachments/assets/08b106f3-56be-4d31-8b21-7431d2619abf)
![8](https://github.com/user-attachments/assets/94269a2a-b4bd-4004-8c12-a1b4dfb76db9)
![9](https://github.com/user-attachments/assets/2ddb9f05-1a33-466d-ba23-5adadb4a6568)
![10](https://github.com/user-attachments/assets/fbf26db0-9c18-40fd-8103-53a5433498ed)
![11 automated hot coll archived for container blob storage using lifecycle management](https://github.com/user-attachments/assets/652d3400-0850-452f-86a7-55e9ca1d65d1)




