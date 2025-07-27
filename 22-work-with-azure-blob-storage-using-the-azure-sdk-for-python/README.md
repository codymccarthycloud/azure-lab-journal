# Azure Blob Storage Lab (Python SDK CLI Version)

```bash
# 1 Clone the Lab Repository
git clone https://github.com/pluralsight-cloud/content-az-204-developing-solutions-for-microsoft-azure.git Extension
```

# 2 Move to the Python Folder
cd Extension/work_with_storage/python/

# 3 Install Required SDK
pip install --user azure-storage-blob

# 4 Upload Your Lab Script
# Use the Azure Cloud Shell upload button to upload SDKsamplecode.py (lands in /home/cloud)

# 5 Move Script Into Project Folder
mv ~/SDKsamplecode.py ~/Extension/work_with_storage/python/

# 6 Execute the Python Script
python SDKsamplecode.py

# 7 Validate Blob Creation
# In Azure Portal → Storage Account → Containers → containerforlab → verify blobforlab exists

## Lab Output Screenshots

![1 configure bash and create a new storage account](https://github.com/user-attachments/assets/a42bcef3-5043-41cb-a1d2-a188c4559499)
![2 git clone create extension cd to the python folder and make simplified readbale SDK python file](https://github.com/user-attachments/assets/8c90183f-07f2-46e6-9736-6549c55ac919)
![3 pip install --user azure-storage blob](https://github.com/user-attachments/assets/0bf0c37b-aa42-493c-b2a3-5c373d4415d4)
![4 move py file into python folder from git clone url and run python SDKsamplecode py](https://github.com/user-attachments/assets/5aeb258e-7d10-411e-ba5e-b2a279a3dac5)
![5 enter connection string from the storage account security networking access keys using the visual studio code editor](https://github.com/user-attachments/assets/546b271d-e95c-413d-b51d-9a5accc1e22b)
![6 python SDKsamplecode py run container creation](https://github.com/user-attachments/assets/d8dde5e1-4dfd-4e08-99eb-e136c90301f1)
![7 blob creation confirmed tweak SDK code until it works](https://github.com/user-attachments/assets/96bd9b96-d741-45ea-a9d0-080b659a0f1c)
![8 blob creation confirmed](https://github.com/user-attachments/assets/77db8136-776d-48fe-9939-600ddfc42ad2)
