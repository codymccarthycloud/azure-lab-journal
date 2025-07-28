# Create a Machine Learning Workspace in Azure

This lab guides you through provisioning a Machine Learning workspace in Azure, preparing the compute resources to run your notebooks.

---

## Learning Objectives

- Create a new Azure Machine Learning Studio workspace
- Understand supporting resources created (Key Vault, Storage Account, App Insights)
- Create a compute instance to host notebooks
- Run a simple notebook to confirm setup
- Shut down compute instance for cost management

---

## Step 1: Provision Machine Learning Workspace

# Create Workspace (via portal or ARM template)

---

### Step 2: Create Compute Instance

In **Azure ML Studio**:
- Navigate:  
  `ML Studio → Workspaces → testwusml01 → Compute → + New Compute Instance`
- Configure:
  - **Name**: `cpu-dev-node`
  - **Region**: `West US`
  - **VM size**: Choose lowest-cost general-purpose option (e.g. `Standard_DS11_v2`) or default recommendation

---

### Step 3: Create a Notebook

In **Azure ML Studio**:
- Navigate:  
  `Notebooks → + New → Python (AzureML) Kernel`
- File Name: `test-notebook.ipynb`
- Paste and run:
  ```python
  print("Hello, world!")

---

## Step 4: Shut Down Compute Instance

Once your notebook is tested and resources are confirmed, it’s important to **stop the compute instance** to avoid unnecessary costs.

In **ML Studio** or via the **Azure Portal**:

- Navigate to:  
  `Compute → Instances → cpu-dev-node → Stop`

 **Tip** Shutting down unused compute helps optimize your budget and maintain clean environments for resource auditing.

---

## Extras

### Role-Based Access Control (RBAC) and Tagging

To ensure proper governance and accountability:

- Assign RBAC roles to users based on permissions required
- Use **tags** like `env:dev`, `owner:cody`, or `purpose:ml-lab` to organize and classify resources

Tags are especially helpful for cost allocation and lifecycle management.

---

### Infrastructure as Code (IaC)

For automation, reference the supporting **ARM template** and lab instructions:

- Use Azure Resource Manager (ARM) templates for consistent workspace creation

This enables reproducibility across environments and teams.

---

## Summary

- Shut down compute to avoid charges
- Implement RBAC and tagging for governance
- Use ARM templates for automation and consistency

---

## Lab Output Screenshots

![1 azure machine learning create workspace](https://github.com/user-attachments/assets/0196df47-e7df-489b-8bd9-83ba6acd734c)
![2 azure machine learning creation naming for enterprise settings](https://github.com/user-attachments/assets/31362180-2730-47eb-b130-7e0246b25232)
![3 machine elarning workspace deployment get arm template](https://github.com/user-attachments/assets/24e88eac-5ee5-4924-878b-bd4adcf7cb18)
![4 machine learning workspace deployment arm template](https://github.com/user-attachments/assets/d6840fde-818b-431e-b1b6-ecea62f8712d)
![5 resource group confirmation](https://github.com/user-attachments/assets/8a08e2a2-b3c5-4113-857e-98e72d34b692)
![6 resource group confirmation](https://github.com/user-attachments/assets/e98fcf17-b4b8-469a-9d00-c3a36e540ee4)
![7 check to see if resources are available in the workspace directly](https://github.com/user-attachments/assets/3afec2f6-b7bf-476b-a18c-160342716212)
![8 launch ml workspace](https://github.com/user-attachments/assets/8070d49f-29d0-4f59-819f-4244ac675e4a)
![10 access azure workspace in ml workspace after launch to create compute](https://github.com/user-attachments/assets/b16eb93a-2093-45aa-b66b-78011963486d)
![11 create compute instance](https://github.com/user-attachments/assets/31acb1eb-350e-4566-833c-04717576b538)
![12 my first notebook in ml workspace](https://github.com/user-attachments/assets/180f780d-0d75-4f93-9254-4d2782398391)
![13 compute created run notebook using compute vm](https://github.com/user-attachments/assets/7ed936b7-d4ed-4e6b-8377-27bb9c7832bc)
![14 notebook is running using the created compute for ml workspace](https://github.com/user-attachments/assets/563568d6-3b60-4b52-9458-0edc3350ffc8)
![15 stop notebook vm](https://github.com/user-attachments/assets/7c0af6b2-67b1-40c7-b909-2d33c0dee902)
![cpu-dev-node create compute](https://github.com/user-attachments/assets/8e783049-98c0-4a83-b981-1acbf02982b3)







