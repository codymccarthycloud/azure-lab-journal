# Deploying Containers to Azure App Service

This guide walks through deploying a Docker-based web app to Azure App Service.

## Prerequisites
- Azure subscription
- Docker image (e.g., hosted on Docker Hub)
- Azure App Service Plan (Linux-based)

## Steps to Deploy

### 1. Sign in to the Azure Portal
Visit [Azure Portal](https://portal.azure.com) and log in.

### 2. Create a Linux Azure App Service
- Navigate to **App Services > + Create**
- Choose:
  - OS: **Linux**
  - Publish: **Docker Container**
- Select **Basic Pricing Plan** to avoid resource limit issues.

### 3. Configure Container Settings
- Under **Docker Options**:
  - Image Source: **Docker Hub**
  - Image Name: `filebrowser/filebrowser` (or any preferred repo)
- Click **Review + Create**

### 4. Verify Deployment
- Access the **App Service URL**
- Confirm the containerized app is running

## Notes
- Use resource group naming convention: `rg-<project>-<env>`
- Example App Name: `test-scus-webapp-stg`  
  *(scus = South Central US, stg = staging)*

## Example Docker Hub Image
```text
https://hub.docker.com/r/filebrowser/filebrowser
```

---

## Lab Output Screenshots

![1 create a webapp container for linux](https://github.com/user-attachments/assets/7cbfbcc3-1c0a-4243-8b09-b68d627fdb98)
![2 configure webapp container using docker](https://github.com/user-attachments/assets/4b815806-fb90-46cf-9f4c-52c6972dd9df)
![3 copy image and tag from docker tags webpage provided](https://github.com/user-attachments/assets/99b2bd01-5481-49ed-8ad3-e983b61a48b7)
![4 image and tag format example](https://github.com/user-attachments/assets/5ed20648-e8f4-4da0-90b0-9fa45269c2f1)
![5 webapp deployed with the docker image and tag container](https://github.com/user-attachments/assets/8883adf6-22a1-46b5-9ddb-9d181b985dfb)
![6 webapp container from docker file browser webpage](https://github.com/user-attachments/assets/fa5bac37-7d99-4cf7-b90c-f59a06435001)
![7 metrics webapp service plan](https://github.com/user-attachments/assets/7a61d37d-57cc-4d23-9f32-997e61645cae)








