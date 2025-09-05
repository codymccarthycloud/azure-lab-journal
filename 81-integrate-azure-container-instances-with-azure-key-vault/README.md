# Integrating Azure Container Instances with Azure Key Vault

## Overview
This guide walks through deploying an Azure Container Instance (ACI) that uses a User-Assigned Managed Identity to securely retrieve secrets from Azure Key Vault.
- Azure subscription
- Resource group
- Azure Key Vault with a secret
- User-Assigned Managed Identity
- Container Instance

## Assign Key Vault Permissions to the Identity
Key Vault > Access policies > Create > Get Secret Permissions > (Name) myUserAssignedIdentity (Object ID)
Replace <your-keyvault-name> and <identity-object-id> with your actual values.

## Create the Azure Container Instance
```bash
az container create \
  --resource-group <your-resource-group> \
  --name myacivault \
  --image mcr.microsoft.com/azure-cli \
  --assign-identity <identity-resource-id> \
  --os-type Linux \
  --cpu 1 \
  --memory 1.5 \
  --command-line "tail -f /dev/null"
```
This creates a Linux-based container with the Azure CLI image and assigns the managed identity.

## Set Parameters Inside the Container CLI

```bash
client_id="<Managed Identity Client ID>"
```

```bash
vault_name="<Vault Name>"
```

```bash
secret_name="mySecret"
```
Then inside the container, authenticate using the identity:

```bash
az login --identity --client-id ${client_id} --allow-no-subscription
```

## Retrieve the Secret from Key Vault
After logging in, run:

```bash
az keyvault secret show \
  --vault-name ${vault_name} \
  --name ${secret_name}
```

This will return the secret value securely using the identity.

## Summary
1	Assign Key Vault permissions to identity
2	Deploy ACI with identity and CLI image
3	Authenticate inside container
4	Retrieve secret using Azure CLI

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/8aa4db3b-7c40-4185-8f60-3cc86e432fb6)
![2](https://github.com/user-attachments/assets/e8a81af5-565c-4bc8-b21f-a8d8b01d1c0b)
![3](https://github.com/user-attachments/assets/1dadecd5-aa3c-4c74-925b-9cffc75cd802)
![4](https://github.com/user-attachments/assets/85e37250-1240-45e2-806f-1cf9749074c0)
![5](https://github.com/user-attachments/assets/45155881-7c24-4081-9cfa-f554262528bf)
![6](https://github.com/user-attachments/assets/cc318c8a-fe71-4545-8567-8f2e44e65cfa)
![7](https://github.com/user-attachments/assets/014a0118-d16f-4986-8c1e-8e65cc28856c)
![8](https://github.com/user-attachments/assets/a81935b9-cd0e-41f6-99ae-8c461c03ca22)
![9](https://github.com/user-attachments/assets/2e6a601e-dafa-4fa7-a139-c9bae7060eba)
![10](https://github.com/user-attachments/assets/ca027057-daf2-4c22-b5e6-4ae1f493a039)
![11](https://github.com/user-attachments/assets/86b575ef-57a4-4373-90e7-4344bec877c3)
![12](https://github.com/user-attachments/assets/307223ad-6bcf-4fde-9e19-9def27d95333)
![13](https://github.com/user-attachments/assets/9fb117fe-f278-43db-ad8b-2f461c06d2c9)
![14](https://github.com/user-attachments/assets/45597209-3fc3-4ccc-b929-ed440d8b02c9)
![15](https://github.com/user-attachments/assets/951d4e81-3c6f-47cf-994d-d0c89d1e4caf)
![16](https://github.com/user-attachments/assets/073c513a-bf19-4db8-a7b0-7be5497f3c15)
![17](https://github.com/user-attachments/assets/0f8a3b1d-7b8c-4087-9478-52832077115e)
![18](https://github.com/user-attachments/assets/19958469-a669-459b-abf9-964304dffeb3)
![19](https://github.com/user-attachments/assets/611fd085-001d-4e7b-a446-ca2c3e449487)
![20](https://github.com/user-attachments/assets/28ea512b-9990-438a-bf2b-9998fa743714)
![21](https://github.com/user-attachments/assets/7122c7fe-b879-491d-a0ae-90a86f32ae31)
![22](https://github.com/user-attachments/assets/8681b3a4-bb5f-4cc2-a154-893657de63c2)

