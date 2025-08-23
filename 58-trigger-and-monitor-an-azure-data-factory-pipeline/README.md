## Trigger and Monitor an Azure Data Factory Pipeline
Trigger an Azure Data Factory pipeline and monitor its execution status using Azure CLI and the Azure Portal.

## Prerequisites
- Azure CLI installed and authenticated
- An existing Azure Data Factory instance
- A published pipeline in your Data Factory
- Resource Group and Data Factory names

## Trigger the Pipeline via Azure CLI
```bash
az datafactory pipeline create-run \
  --resource-group <your-resource-group> \
  --factory-name <your-data-factory-name> \
  --pipeline-name <your-pipeline-name> \
  --parameters <optional-parameters-as-json>
```    

Example:
```bash
az datafactory pipeline create-run \
  --resource-group rg-demo \
  --factory-name adf-demo \
  --pipeline-name CopyPipeline \
  --parameters '{"sourceFile": "input.csv", "destinationFile": "output.csv"}'
```
This command returns a runId which you’ll use to monitor the pipeline.

## Monitor Pipeline Run via Azure CLI
```bash
az datafactory pipeline-run show \
  --resource-group <your-resource-group> \
  --factory-name <your-data-factory-name> \
  --run-id <run-id>
```    
Example:
```bash
az datafactory pipeline-run show \
  --resource-group rg-demo \
  --factory-name adf-demo \
  --run-id 12345678-abcd-efgh-ijkl-9876543210mn
```
This returns the current status of the pipeline run:

- InProgress
- Succeeded
- Failed
- Cancelled

## Monitor in Azure Portal
Go to your Azure Data Factory resource.
Click on Monitor in the left-hand menu.
Select Pipeline Runs.
Filter by time or pipeline name to view recent executions.
Click on a run to view activity details, logs, and error messages.

---

## Lab Output Screenshots 

![1](https://github.com/user-attachments/assets/d790a774-ce21-4162-b671-de7ec5f910f5)
![2](https://github.com/user-attachments/assets/1f20f386-ac48-43ab-8ae7-656b6087669b)
![3](https://github.com/user-attachments/assets/0aba8bcd-f589-4223-aaad-e051f110aca5)
![4](https://github.com/user-attachments/assets/86226cb8-e1ed-4151-8297-78cb00ca122f)
![5](https://github.com/user-attachments/assets/ac98c01c-3450-48a2-a896-604eb23bdaf6)
![6](https://github.com/user-attachments/assets/7ed8cf52-5f55-47c2-8312-7e5a073d8b22)
![7](https://github.com/user-attachments/assets/6d805f6a-38b4-4683-bcb9-3bd761914a03)
![8](https://github.com/user-attachments/assets/2808a277-dcca-4700-9e8a-45926cc61228)
![9](https://github.com/user-attachments/assets/85bd4457-423e-4158-829b-3a10e6236cd9)


