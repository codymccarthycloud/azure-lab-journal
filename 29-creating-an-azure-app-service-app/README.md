# Creating an Azure App Service App Using Portal and CLI

This lab walks through the process of creating an Azure App Service app using both the Azure Portal (desktop interface) 
and Azure CLI via Cloud Shell. You’ll deploy a web app, configure hosting, and validate the resource creation the GUI and CLI.

---

## Lab Objectives

- Deploy an App Service app using Azure Portal
- Configure App Service Plan with Basic pricing
- Create a Web App using Azure CLI in Cloud Shell
- Understand differences between manual and scripted provisioning

---

## Part 1: Create Web App Using Azure Portal

### Steps:

1. Log in to Azure Portal
2. Click **Create a resource → Web App**
3. Configure the basics:
   - **Subscription**: Use provided lab subscription
   - **Resource Group**: `873-0536a99f-creating-an-azure-app-service-app`
   - **Name**: `test-scus-webaapp-homeserver`
   - **Region**: `South Central US`
   - **Runtime stack**: Select a runtime (e.g., `.NET`, `Node.js`, `Python`)
   - **Operating System**: Typically `Linux`
   - **App Service Plan**: Create new plan using **Basic (B1)** tier

4. Click **Review + Create**, then **Create**

Once deployed, your web app is visible in the portal dashboard.

---

## Part 2: Create Web App Using Azure CLI

### Prep

Open **Cloud Shell** → Select **Bash**  
On first use:  
- Choose **Advanced Settings**
- Use the provided storage account
- Create a new file share

### CLI Commands

```bash
# Create Web App
az webapp create \
  --name $APP_NAME \
  --resource-group $RG_NAME \
  --plan $PLAN_NAME \
  --runtime "DOTNET:9"
```

### Additional practice set variables

```bash
RG_NAME="873-0536a99f-creating-an-azure-app-service-app"
APP_NAME="test-eus-webapp-01"
PLAN_NAME="test-eus-web-plan"
LOCATION="eastus"
```

### Create App Service Plan (Required for Hosting)

```bash 
az appservice plan create \
  --name $PLAN_NAME \
  --resource-group $RG_NAME \
  --location $LOCATION \
  --sku B1 \
  --is-linux
```

## Lab Output Screenshots

![1 navigate to app services to create a web app](https://github.com/user-attachments/assets/8fd829f8-3fc9-45cf-baf9-4b76661fb93e)
![2 create web app](https://github.com/user-attachments/assets/4c0522f3-3757-45be-95ac-ea0418853cd6)
![3 web app created browse](https://github.com/user-attachments/assets/a3c3b9a9-88c1-492b-84f8-b89f164e04ae)
![4 web app is running and waiting for your content](https://github.com/user-attachments/assets/9dd8a3e2-8467-4d7e-bcbd-fada8a646625)
![5 use cli az webapp create -g -p -n -r dotnet 9](https://github.com/user-attachments/assets/e9373ccb-6a6c-47e0-baaa-de3563c79ed7)

