# Limit Access to Azure Storage Account Using SAS URI

## Prepare Testing Environment
- Log in to the Azure Portal using lab credentials in **Incognito mode**.
- Connect to the pre-provisioned VM via **RDP**:
  - **Username**: `cloud_user`
  - **Password**: *(from lab credentials)*
- Launch **Azure Storage Explorer** on the VM.
- Choose **Attach to a resource > Storage account or service > Shared access signature URL (SAS)**.
- Leave the connection dialog open and minimize the VM.

## Create Storage Container and Upload Files
- In the Azure Portal, navigate to the storage account (starts with `pslab`).
- Go to **Data storage > Containers**.
- Create a new container named `container1`.
- Upload two sample `.txt` files to the container.

## Generate SAS Token
- In the storage account, go to **Settings > Configuration**.
- Enable **Allow storage account key access** and click **Save**.
- Navigate to **Security + networking > Shared access signature**.
- Configure the SAS token:
  - **Allowed services**: Blob
  - **Allowed resource types**: Service, Container, Object
  - **Allowed permissions**: Read, List
  - **Allowed protocols**: HTTPS only
- Click **Generate SAS and connection string**.
- Copy the **Blob service SAS URL** and save it securely.

## Test SAS-Based Access
- Return to the VM and paste the SAS URL into Storage Explorer.
- Connect and verify `MyLabCnx` appears in the Explorer pane.
- Navigate to `container1` and confirm the two uploaded files are visible.
- Attempt to delete a file — the action should **fail**, confirming limited permissions.

---

## Observations

- SAS tokens provide fine-grained, time-bound access to storage resources.
- Read/List permissions worked as expected; delete operations were blocked.
- Using Storage Explorer with SAS is ideal for secure, scoped access without exposing account keys.

---

## Completion Notes

- Successfully created and tested a SAS token for Azure Blob Storage.
- Verified permission boundaries using Azure Storage Explorer.
- Demonstrated secure access control without full account credentials.

Tip: Always restrict SAS tokens to the minimum required permissions and set expiration dates to reduce security risks.

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/31690974-33b7-4156-868f-e06f7438503f)
![2](https://github.com/user-attachments/assets/b50a7eff-9836-4603-ab3d-fa904480a936)
![3](https://github.com/user-attachments/assets/155f58fe-431b-4f79-b1f1-0274a6df1ca3)
![4](https://github.com/user-attachments/assets/6da8fa83-9bdf-439f-9753-3b8060e5d752)
![5](https://github.com/user-attachments/assets/41d5eedc-69a0-4c53-bc02-532c8f508372)
![6](https://github.com/user-attachments/assets/d0d92757-e504-4538-9308-33fc8bbdae58)
![7](https://github.com/user-attachments/assets/c52fafae-5883-4fcd-9090-00f8d1ec7368)
![8](https://github.com/user-attachments/assets/b94d4cdd-41e1-440d-9978-1fe32dab7f63)
![9](https://github.com/user-attachments/assets/a9f5a3dc-8cf9-4cfa-bd93-11f0fb6453de)
![10](https://github.com/user-attachments/assets/56eb3028-f435-4fc3-8ed6-9d4f4a3dd0f9)
![11](https://github.com/user-attachments/assets/846195bc-6444-4b84-8125-4d93b51ecd1d)
![12](https://github.com/user-attachments/assets/45f065fc-5fd4-436a-8ac6-ffcf0fd0836c)
![13](https://github.com/user-attachments/assets/315b2683-3f14-411a-af0b-02d38e571637)
![14](https://github.com/user-attachments/assets/155fb18a-c453-4ba4-bb6a-db9bafe987f7)
![15](https://github.com/user-attachments/assets/cad63068-00ed-4780-8ef0-1dcb7748ca93)
![16](https://github.com/user-attachments/assets/8146e290-57eb-4863-b193-26e92b0624c4)
![17](https://github.com/user-attachments/assets/5c911f86-36f2-48f3-952e-c821e1dd06bf)
![18](https://github.com/user-attachments/assets/1657f974-aee5-4000-8aef-8878a46b15c0)
![19](https://github.com/user-attachments/assets/96f76d5d-40c2-4bf1-b6f9-84e6a85af172)
![20](https://github.com/user-attachments/assets/1cf2e987-f78d-42a9-aa86-a64f7808cf6c)
![21](https://github.com/user-attachments/assets/506e573f-5160-4e7a-8138-cd62ee084c75)
![22](https://github.com/user-attachments/assets/60a40645-0c8a-4ca6-a6ec-c6dda41c59dd)
![23](https://github.com/user-attachments/assets/8e4d5df6-190e-4be3-b54c-1119c4184859)
![24](https://github.com/user-attachments/assets/162ecba2-b504-4fae-b60c-1eb7a7c6dddb)
![25](https://github.com/user-attachments/assets/88f258d2-f921-480e-ae6d-1d3ed4759af0)
![26](https://github.com/user-attachments/assets/d2829692-6cfe-4af9-966c-e8c8d091f2e0)
![27](https://github.com/user-attachments/assets/470ddc3d-ca31-4f1b-aec5-fee5b05e8c57)
![28](https://github.com/user-attachments/assets/9c05180f-4510-4a8e-9c43-6878c6f59cdc)

