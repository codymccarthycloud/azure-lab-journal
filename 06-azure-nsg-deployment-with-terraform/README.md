# Azure NSG Deployment with Terraform – Lab Documentation

## Lab Overview
This lab demonstrates deploying an Azure Network Security Group (NSG) using Terraform through Azure Cloud Shell. It covers file creation, uploading to Cloud Shell, verifying contents, executing Terraform commands, and confirming deployment via the Azure Portal.

---

## Step 1: Create the Terraform File Locally

- Open a text editor (Notepad, VS Code, etc.)
- Paste the provided NSG Terraform configuration code
- Save the file as `lab.tf` ( Be sure it's `.tf` not `.txt`)
  - In Notepad: Select "All Files" from the Save dialog
  - Type: `lab.tf`

---

## Step 2: Upload the File into Azure Cloud Shell

- Go to [https://portal.azure.com](https://portal.azure.com)
- Launch **Azure Cloud Shell** from the top menu (select **Bash**)
- When prompted, select **Show Advanced Settings**
  - Use pre-selected Resource Group and Storage Account
  - In "File Share", choose **Create new** and name it `console`
  - Click **Attach Storage**

- After the shell initializes, click the **Upload/Download** button above the terminal
  - Upload your `lab.tf` file from your local machine

---

## Step 3: Verify the Upload

- In the Cloud Shell terminal, confirm the file exists:
```bash
  ls
```

---

# Azure NSG Deployment – Lab Completion & Output

##  Conclusion

This Terraform lab successfully deployed an Azure Network Security Group (NSG) using `lab.tf` in Cloud Shell. All setup was completed via Bash with manual file upload and confirmation of contents using basic CLI commands.

The NSG was verified in the Azure portal under the designated resource group, with inbound/outbound rules created as defined in the configuration file.

---

## Terraform CLI Workflow

```bash
terraform init
terraform plan
terraform apply
```

--- 

## Lab Output Screenshots

![creating a lab tf file for NSG with Terraform in azure cli entering in the resource group manually](https://github.com/user-attachments/assets/55f2673f-f12a-464d-ad53-9baa13e5f49b)
![upload a file into bash and view it](https://github.com/user-attachments/assets/cbda7d24-0197-43bf-9060-45f158ed76a9)
![terraform init in cli](https://github.com/user-attachments/assets/04cfe555-e350-4855-b7ba-c20caf4ff43d)
![terraform plan view uploaded Lab tf](https://github.com/user-attachments/assets/7e60f44d-6347-4463-ac28-0be1840ffe75)
![terraform apply azure refresh resource group to confirm NSG](https://github.com/user-attachments/assets/ffc3c194-9630-45da-9137-cc8e3bbbd2f2)

