# Expire Data Based on Age in Azure Blob Storage


### Scenario
You have a container named holidaysale with an img folder containing images. You want to automatically delete blobs in this folder 30 days after creation.

## Upload Images to Blob Storage
Go to the GitHub repo to download sample images.

In the Azure Portal:
Navigate to your Storage Account.
Click Containers.
Create a container named holidaysale.
Inside it, create a folder named img.
Upload the images to this folder.

## Add Lifecycle Management Policy
In the Storage Account menu, find Data Management > Lifecycle Management.
Click + Add a rule.
Configure the rule:
Scope: Limit to blobs with prefix holidaysale/img/
Blob type: Base blobs
Action: Delete
Condition: Blob was created more than 30 days ago

```json
{
  "rules": [
    {
      "enabled": true,
      "name": "expire-img-data",
      "type": "Lifecycle",
      "definition": {
        "filters": {
          "blobTypes": ["blockBlob"],
          "prefixMatch": ["holidaysale/img/"]
        },
        "actions": {
          "baseBlob": {
            "delete": {
              "daysAfterCreationGreaterThan": 30
            }
          }
        }
      }
    }
  ]
}
```

### Conclusion
Blobs in the holidaysale/img/ folder will be automatically deleted 30 days after their creation date, helping you manage storage costs and data retention.

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/58b338a6-c32f-494c-9f7c-f6b7603fade3)
![2](https://github.com/user-attachments/assets/b7b2fe48-438b-4f9a-9971-c27173bf7f82)
![3](https://github.com/user-attachments/assets/bf80f7c8-4ced-4830-ad08-5205b0386b34)
![4](https://github.com/user-attachments/assets/d25972b3-79a5-4d1b-b31c-bcdd138f6276)
![5](https://github.com/user-attachments/assets/21140efe-7ba9-4c36-ac66-4d6868a01c1c)
![6](https://github.com/user-attachments/assets/2abfc69c-3d8e-4d05-b95e-41ee6675da72)
![7](https://github.com/user-attachments/assets/bff6cb87-30b5-4599-af7d-8dde74feef12)
![8](https://github.com/user-attachments/assets/1c076a08-8334-475b-a03f-b678a3a335f8)
![9](https://github.com/user-attachments/assets/428953ae-1d00-48b9-9fba-c32fc0138533)
![10](https://github.com/user-attachments/assets/9957cac3-2003-492b-95fc-522217fa8d81)
![11](https://github.com/user-attachments/assets/82b21975-12be-4334-9994-d531ab88ea95)
![12](https://github.com/user-attachments/assets/be0db7d4-d930-48d8-8578-42bee5501d55)

