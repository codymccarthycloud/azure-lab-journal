# Create and Save a Reusable ARM Template from an Existing Azure SQL Database


This guide outlines how to generate and save a reusable Azure Resource Manager (ARM) template from an existing Azure SQL Database. 
This enables consistent deployments across environments and simplifies developer onboarding.

## Steps

## Navigate to the Resource
- Go to the **Resource Group** containing your SQL Database and Server.
- Select either the **SQL Database** or the **SQL Server** (both produce the same template).

## Export the ARM Template
- In the left-hand menu, click **Export template**.
- Uncheck **Include parameters** to simplify the template (optional).
- Click **Download** to save the `.zip` file locally.
- Extract the `template.json` file from the downloaded archive.

## Save as a Template Spec
- In the Azure Portal search bar, type **Template Specs** and select it.
- Click **+ Create** or **Import template**.
- Upload the extracted `template.json`.
- Fill in the following fields:
  - **Name**: `mySampleLabTemplate`
  - **Resource Group**: Select an existing group
  - **Description**: Specify deployment purpose
  - **Version**: `1.0`
- Click **Review + Create**, then **Create**.

## Deploy the Template
- From the Template Spec, click **Deploy**.
- Provide parameter values if required.
- Note: In restricted lab environments, deployment may fail — use this to explore troubleshooting steps.

## Conclusion
You now have a reusable ARM template stored as a Template Spec, ready for consistent deployments across your team.

**Why You Should Use Parameters in Enterprise Settings**
Even though it's technically optional, parameters are critical for:
- Environment-specific deployments (dev/test/prod)
- Security (e.g., passing secrets via Key Vault)
- Automation (CI/CD pipelines, GitHub Actions)
- Governance (auditing and version control)

Embed Parameters in the Template
You can define default values directly in the parameters section of the ARM template:

```json
"parameters": {
  "sqlServerName": {
    "type": "string",
    "defaultValue": "myDefaultServer"
  }
}
```

Embed Parameters with Default Values (Inside the Template)
If you want the template to be self-contained and reusable 
without needing a separate parameters file, you can define 
parameters inside the template like this:

```json
{
  "$schema": "...",
  "contentVersion": "1.0.0.0",
  "parameters": {
    "sqlServerName": {
      "type": "string",
      "defaultValue": "myDefaultServer"
    },
    "location": {
      "type": "string",
      "defaultValue": "eastus"
    }
  },
  "resources": [
    // your resources here
  ]
}
```

You don’t paste it into the template. Instead, you:
Upload only the template.json to your Template Spec.
Provide the parameters.json when you deploy the template — either through the portal, CLI, or pipeline.

**Best Practice for Enterprise Use**
Keep the template generic and reusable.
Use external parameter files for environment-specific values.
Avoid hardcoding unless it’s a lab or demo.

| Feature                                                | ARM Template   | Parameters     |
|--------------------------------------------------------|----------------|----------------|
| Defines resource types and structure                   |  Yes           |  No            |
| Sets default values for deployment                     |  Sometimes     |  Yes           |
| Allows customization per environment                   |  No            |  Yes           |
| Enables reuse across teams/projects                    |  Limited       |  Strong        | 
| Supports secure value injection (e.g., secrets)        |  No            |  Yes           |
| Used for CI/CD automation                              |  With limits   |  Essential     |

Parameters enable flexibility, security, and automation in deployment workflows.

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/665a7ebb-b49b-4784-8702-14ad4cd12933)
![2](https://github.com/user-attachments/assets/29feaddf-2fac-4d7f-9610-ea230616079f)
![3](https://github.com/user-attachments/assets/934f7dc9-e577-4066-a2f5-cf69efd2a9e3)
![4](https://github.com/user-attachments/assets/3422394a-1797-41c8-906e-a8ba3efa94f1)
![6](https://github.com/user-attachments/assets/ccd1ea1a-3cd1-4152-917a-869c7db4c16a)
![5](https://github.com/user-attachments/assets/ae8089fd-7083-4a0f-a8b3-46709e4cbbb0)
![7](https://github.com/user-attachments/assets/8987d5c7-b6b6-4961-99e7-c4991e6407d6)
![8](https://github.com/user-attachments/assets/6cdcf4b5-730c-4ed8-a2e2-b5e192231fab)
![9](https://github.com/user-attachments/assets/12f94a2a-5869-484b-81d9-3ce61da211f7)
![10](https://github.com/user-attachments/assets/82ed2cd8-4250-4dda-a01e-1d8336c8cf2b)
![11](https://github.com/user-attachments/assets/40bbfd62-35e6-452f-a2bd-5c4f3e34f888)

