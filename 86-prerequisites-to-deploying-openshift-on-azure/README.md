# Prerequisites to Deploying OpenShift on Azure

This guide walks through the essential setup steps before deploying OpenShift on Azure, 
including configuring Cloud Shell, creating a Key Vault, generating SSH keys, and storing secrets.

---

## Configure Azure Cloud Shell

- Log in to the Azure Portal.
- Click the **Cloud Shell** icon in the top-right corner.
- Choose **Bash** as your shell environment.
- If prompted, configure storage:
   - Use the same location as your resource group.
   - Create a new storage account.
   - Create a new file share named `okdcloudshell`.
- Click **Create Storage** and wait for confirmation.

---

## Create a Key Vault

Use Azure CLI in Cloud Shell to create a Key Vault:

```bash
az keyvault create \
  --resource-group <your-resource-group> \
  --name keyvaultOKD \
  --enabled-for-template-deployment true
```

If keyvaultOKD is already taken, append a random number to make it unique.

## Generate SSH Keys
Generate SSH keys and store them in your .ssh directory:

```bash
ssh-keygen -f ~/.ssh/id_rsa -t rsa -N ""
```
Do not use a passphrase.

## Store SSH Key in Key Vault
Store the private key as a secret in the Key Vault:

```bash
az keyvault secret set \
  --vault-name keyvaultOKD \
  --name keysecret \
  --file ~/.ssh/id_rsa
```

## Summary
What Does keyvaultOKD Mean?
OKD: This stands for Origin Kubernetes Distribution, which is the upstream open-source version of Red Hat OpenShift.
Kubernetes is the engine—an open-source container orchestration platform that automates deployment, scaling, and management of containerized applications. It’s powerful, but raw. You get the core functionality, but you have to assemble the rest yourself.

OpenShift, on the other hand, is the car built around that engine. It’s a fully integrated platform that includes Kubernetes plus:
- Built-in security policies and role-based access control
- Developer tools like source-to-image (S2I) and integrated CI/CD pipelines
- Registry and image management
- Monitoring, logging, and metrics
- Enterprise support from Red Hat

By completing these steps, you've:
- Set up Cloud Shell
- Created a secure Key Vault
- Generated and stored SSH credentials

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/68c385a2-f7cd-410e-85b1-6f9294cac272)
![2](https://github.com/user-attachments/assets/67be85f1-07ad-4779-bd83-5c95e2e872ea)
![3](https://github.com/user-attachments/assets/0cfc7681-4da8-47fb-bcad-bebcfc85ba7c)
![4](https://github.com/user-attachments/assets/8ecf7ecf-72ec-41c8-aa41-2855262f20f5)
![5](https://github.com/user-attachments/assets/bc2c7156-653a-4c68-9f7b-f336f8a3d13f)
![6](https://github.com/user-attachments/assets/a7ab7bd7-74eb-4ae2-a44b-be993269c6ce)
![7](https://github.com/user-attachments/assets/a84cd02e-fc66-4138-90e1-48682921d291)
![8](https://github.com/user-attachments/assets/0bbc74c0-f491-4626-94c0-f961933496db)
![9](https://github.com/user-attachments/assets/4623250e-6880-4b64-9aa7-418bb401a17d)
![10](https://github.com/user-attachments/assets/c2e763c2-0fa3-412a-99b4-335149b746d4)
![11](https://github.com/user-attachments/assets/982e4d16-09d1-4f35-a968-b655581454f3)



