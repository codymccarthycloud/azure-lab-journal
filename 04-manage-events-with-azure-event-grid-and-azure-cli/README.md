# Manage Events with Azure Event Grid and Azure CLI - Lab Summary

## Part 1 – Setup via Azure CLI (Cloud Shell)

1. Open Azure Portal and launch Cloud Shell (Bash).  
2. Set up a **new backing storage account** (do not use the pre-deployed `pslab...` one).
3. Install Event Grid extension in the CLI and retrieve the resource ID of the existing storage account:
```bash
az extension add --name eventgrid   
```
```bash
   storageid=$(az storage account show -n <storage-account-name> -g <resource-group-name> --query id --output tsv)
```
4. Create an Event Grid System Topic on the existing storage account
```bash
az eventgrid system-topic create \
  -g <resource-group-name> \
  -n blobsystemtopic \
  --topic-type Microsoft.Storage.StorageAccounts \
  --location "South Central US" \
  --source $storageid
```
---

## Part 2 - Switch to Azure Portal (GUI/Desktop)

Navigate to your deployed storage account (pslab...).

Check if a Storage Queue exists. If not, create one (name it anything).

Create an Event Grid Event Subscription:

Scope: the System Topic (blobsystemtopic)

Destination: the storage queue created above

Filter: BlobCreated and BlobDeleted events

Note: Event Subscription cannot be created via CLI in this lab due to security restrictions.

## Part 3 – Test Event Flow
Upload a blob file (like .json) to the container in your storage account.

Head to your storage queue and confirm a message (e.g., PutBlob) has been received.

---

### Summary
You're wiring up an event-driven pipeline:

Blob Storage = triggers

System Topic = watches

Event Subscription = routes

Storage Queue = holds message

Next Service = can consume the event

All using Azure CLI for setup and Portal for final steps. Done like a pro. 

---

## Conclusion
- Complete lab using CLI only
- Complete lab using GUI only
- Watch educational videos on Event Grid practical applications and uses

---

## Lab Output Screenshots

![CLI AZ Eventgrid storageid system-topic create](https://github.com/user-attachments/assets/9af86ab5-d584-4007-b645-34a22febea8b)
![Create Queue Queue Subscription Storage Queue Event Types](https://github.com/user-attachments/assets/a2d12a8e-6234-4516-8bf1-c15faf78a862)
![uploading a deployable template parameters zip blob](https://github.com/user-attachments/assets/075bd28f-4989-4465-94bb-ea468b81edb6)
![PutBlob event](https://github.com/user-attachments/assets/acf30164-d4fa-49b0-b74a-f1c10b1ee541)


