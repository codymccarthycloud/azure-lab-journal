# Build and Run a Container Using Azure ACR Tasks
Create a container registry, building a Docker image, and running it using Azure ACR Tasks—all from the Azure Cloud Shell.


## Start Azure Cloud Shell
Click the Cloud Shell icon ( >_ ) in the Azure portal:
- Select Bash

Mount the storage account:
- Choose Select existing storage account.
- Select the provided Resource Group and Storage Account.
- Create a file share named fileshare.

## Create a Container Registry
Replace <RESOURCE_GROUP_NAME> with your actual resource group name:

```bash
az acr create --resource-group <RESOURCE_GROUP_NAME> \
  --name acrbuildcontainer425 \
  --sku Basic \
  --admin-enabled true
```

## Create a Dockerfile
Navigate to your Cloud Shell drive and create a simple Dockerfile:

```bash
cd /home/cloud/clouddrive
echo "FROM hello-world" > Dockerfile
```

## Build and Push the Image to ACR
Use ACR Tasks to build and push the image:

```bash
az acr build --image sample/hello-world:v1 \
  --registry acrbuildcontainer425 \
  --file Dockerfile .
```
Once complete, verify the image in the Azure portal under your container registry.

## Run the Container
Execute the container directly from ACR:

```bash
az acr run --registry acrbuildcontainer425 \
  --cmd '$Registry/sample/hello-world:v1' /dev/null
```

## Conclusion
You've successfully built and run a container using Azure ACR Tasks without needing Docker installed locally. 
This is a powerful way to streamline container workflows directly in the cloud.

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/5fc409a8-c41b-412c-95f1-747470d065df)
![2](https://github.com/user-attachments/assets/fba8a4e1-42b6-41a3-9b6d-4edc27b92a6a)
![3](https://github.com/user-attachments/assets/3d17e339-60fd-4412-b463-e171b5b790c8)
![4](https://github.com/user-attachments/assets/e3dfbd72-da39-4e33-84d8-9f59a54a30f6)
![5](https://github.com/user-attachments/assets/0c98c47f-2032-4c24-ae1f-356688d803b5)
![6](https://github.com/user-attachments/assets/e1ec3a32-5e91-4398-8361-0abdd8b94e62)
![7](https://github.com/user-attachments/assets/0769e85a-d388-4840-a370-b0188f5bb244)
![8](https://github.com/user-attachments/assets/eca2e44c-df4c-4693-b880-3b0030c74816)
![9](https://github.com/user-attachments/assets/8f96b3eb-c25f-48e0-86ab-1f6921c9bce1)
![10](https://github.com/user-attachments/assets/485fc12f-c893-4f36-9e45-6e22bf18a4f4)
