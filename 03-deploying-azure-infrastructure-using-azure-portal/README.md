# Azure Storage Deployment Lab

This repo supports hands-on learning from the "Deploying Azure Infrastructure Using Azure Portal" lab, 
and expands it to support repeatable infrastructure deployments using Azure Resource Manager (ARM) templates and CLI.

## Objectives
- Configure and deploy a basic Storage Account through the Azure Portal.
- Save and structure the deployment as an ARM template and parameters file.
- Redeploy infrastructure using Azure CLI for repeatability.
- Explore Infrastructure as Code (IaC), DevOps, and CI/CD tooling.

## Folder: StorageDeployment
- `template.json`: ARM blueprint for your storage setup.
- `parameters.json`: Customizable values for a single deployment (can be reused or edited for different environments).

## CLI Deployment
```bash
az deployment group create \
  --resource-group <your-resource-group> \
  --template-file template.json \
  --parameters @parameters.json
```

### Additional Insights
- Use "    " when a desktop folder has a space in the name (e.g. cd ~/Desktop/"Storage Deployment") (e.g. az deployment create group -r new group --template.name...)
- Formatting desktop folders holding ARM templates and parameters for ease of use when deploying in Azure CLI.

---

## Insights into Editing `parameters.json`

Here’s what makes this powerful:

- **Change values on the fly** (e.g., location, storage name) to fit any environment. Sequencing versatility and adapting the template to lowercase 
(e.g., storageAccountName, storageaccountname) for ease of use in the CLI.
- **Maintain separate files** for dev/test/prod for clear separation.
- **Test and tweak without editing the template** great for version control and team collaboration.

You can override specific parameters like so:
```bash
az deployment group create \
  --resource-group GroupB \
  --template-file template.json \
  --parameters storageAccountName=codystorage location=canadacentral
```

---

## Conclusion 
  - Noticeable progress in understand key concepts of using the CLI. Identifying and exploring cloud related terminology and roles through practical hands on experience.

---

## Lab Output Screenshots

![download storage account resource template](https://github.com/user-attachments/assets/b7b63070-9ae7-44e8-8ed3-3cedadbf0333)
![exported storage account template and parameters running back into the CLI](https://github.com/user-attachments/assets/e7712c67-b1fb-456b-bb0e-3453caf0ad07)

![unzipping downloaded storage account resource template in a storage deployment folder](https://github.com/user-attachments/assets/cae1fb85-c582-453a-be3e-497072956ae5)
![locate desktop folder and deploy ARM template and parameters using azures CLI](https://github.com/user-attachments/assets/71efe59e-0f08-4974-b6da-ece968429d5d)

