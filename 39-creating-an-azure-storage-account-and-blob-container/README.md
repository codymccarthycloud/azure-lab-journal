# Creating an Azure Storage Account and Blob Container


## Lab Overview
- **Platform**: A Cloud Guru via Pluralsight
- **Lab Duration**: ~46 minutes
- **Lab URL**: [Lab on Pluralsight](https://app.pluralsight.com/hands-on/labs/a79fbb00-1fa0-4f0e-8477-15d29cf8199c?ilx=true)

---

## Learning Objectives
1. Log in to Azure using provided credentials.
2. Create a uniquely named storage account.
3. Create a blob storage container named `my-container`.
4. Upload files to the blob container.

---

## Step-by-Step Instructions

### 1. Create a Storage Account
- Go to **Storage accounts** → **Create**.
- Select:
  - **Subscription**: Provided by the lab
  - **Resource group**: `919-d0460987-creating-an-azure-storage-account-and`
  - **Name**: Must be globally unique (e.g., `storagedemo-cm`)
  - **Region**: Use the same region as resource group
  - **Performance**: Standard
  - **Redundancy**: Locally-redundant storage (LRS)
- Click **Review + Create** → **Create**

### 2. Create a Blob Container
- Go to your newly created Storage Account
- Navigate to **Containers** → **+ Container**
- Name it `my-container`
- Access level: Private (no anonymous access)

### 3. Upload Files to the Container
- Open `my-container` in the Azure Portal
- Click **Upload** → Select files from your local Downloads folder
- Confirm and check that blob objects are listed

---

## Completion
You now have a functioning Azure Storage Account and Blob container with uploaded blobs from your device.

---

## Lab Output Screenshots

![1 create a storage account using the gui](https://github.com/user-attachments/assets/39df5660-cc80-4cd0-a1ce-612c828b4e7d)
![2 storage account container logs](https://github.com/user-attachments/assets/fb2646f6-f78c-46ca-b607-6834f0871edc)
![3 new container](https://github.com/user-attachments/assets/5e4931e1-6d67-49dc-a734-2fa7d547692a)
![4 upload files to storage account container blob container](https://github.com/user-attachments/assets/a2048780-1a71-45d3-831e-69a0d6b174eb)
![5 advanced upload settings hot cool](https://github.com/user-attachments/assets/2e4f930f-d261-4e52-8f65-80b7283bb611)
