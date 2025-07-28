# Working with Variables and Pipelines in Azure PowerShell

This hands-on lab walks through the use of variables and pipelines in Azure PowerShell via the Azure Cloud Shell. 
You’ll filter and manipulate Azure resources with PowerShell and prepare automation scripts suitable for CI/CD workflows.

---

## Learning Objectives

- Use variables to store data and results
- Apply pipelines for chaining commands
- Filter Azure resources based on Kind, Location, etc.
- Link PowerShell logic to Azure DevOps CD pipelines

---

## Step 1: Define Variables

Variables store data or command output so it can be reused or filtered.

### List All Azure Resources
```powershell
$Resources = Get-AzResource
$Today = (Get-Date).DateTime

$Resources | Format-List

$Resources | Where-Object {$_.Kind -eq 'Storage'}

$Resources | Where-Object {$_.Kind -notlike 'Storage'}

$Resources | Where-Object {$_.Location -eq 'westus'}

$Resources | Select-Object Name, Location
```

---

## CI/CD Relevance

PowerShell automation using variables and pipelines is often used in CD pipelines to:
- Provision infrastructure
- Apply filters before actions
- Monitor cost
- Tag and organize resources

```Yaml
- task: AzurePowerShell@5
  inputs:
    azureSubscription: 'MyConnection'
    ScriptType: 'InlineScript'
    Inline: |
      $Resources = Get-AzResource
      $StorageResources = $Resources | Where-Object { $_.Kind -eq 'Storage' }
      $StorageResources | ForEach-Object { Write-Host $_.Name }
    pwsh: true
```

---

## Lab Output Screenshots 

![1 configure powershell with the existing storage account](https://github.com/user-attachments/assets/d069f47d-da34-4f1e-bc5f-10a893498107)
![2 set $Resources $Today Get Date Date Time](https://github.com/user-attachments/assets/9573ee98-dc08-4500-9148-a4e307d610e2)
![3 resources format list](https://github.com/user-attachments/assets/cea01280-fb13-434c-bad5-cde91d8569ac)
![4 resources format list wide](https://github.com/user-attachments/assets/91490e52-d376-4453-8db1-f51c101a71e6)
![5 resources where object kind storage](https://github.com/user-attachments/assets/ef42fbb3-06f2-4043-9bcd-fd24c86381c4)
![6 resources where object kind notlike storage](https://github.com/user-attachments/assets/28283574-de39-475e-bf10-00501b14d212)
![7 resources where object location eq westus](https://github.com/user-attachments/assets/a1ae747b-875e-4063-ae6c-8cc766e2d7c3)









