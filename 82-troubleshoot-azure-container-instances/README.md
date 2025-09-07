# Troubleshooting Azure Container Instances
This guide walks through the process of diagnosing and resolving issues with 
Azure Container Instances (ACI), including log analysis, container redeployment, and connectivity checks.

### Prerequisites
Access to the Azure Portal
A resource group with deployed container instances
Permissions to create and link a Log Analytics Workspace

## Deploy Log Analytics Workspace

In Azure Portal:
- Go to your Resource Group.
- Click "Create" and search for "Log Analytics Workspace".
- Select it and click "Create".
- Name it `containerlogs`.
- Skip tags, review, and click "Create".

## Connect ACI to Log Analytics Workspace

For each container group:
- Open the container group.
- Navigate to Monitoring > Logs.
- Ensure the workspace is set to `containerlogs`.
- Click "Configure".
- Wait for deployment to complete.
Repeat for all container groups.

## Diagnose Navigation Error

Check container accessibility:
- Open `acilinuxwebcontainergroup01` and copy its public IP.
- Paste into browser – observe error.
- Repeat for `acilinuxwebcontainergroup02` – confirm it works.

# Compare container properties:
- Check port settings under Settings > Properties.
- Note discrepancies between the two containers.
- Redeploy Misconfigured Container

# Use Azure Cloud Shell (Bash):
```bash
az container create \
  --resource-group <YourResourceGroupName> \
  --name acilinuxwebcontainergroup01 \
  --image mcr.microsoft.com/azuredocs/aci-helloworld \
  --os-type Linux \
  --ports 80 \
  --memory 2 \
  --cpu 1 \
  --ip-address Public
```
Verify deployment and port 80 update by accessing the new public IP in a browser.

## Analyze Logs in Log Analytics
Run these queries in Logs (containerlogs workspace):

```kusto
ContainerInstanceLog_CL
| limit 50

ContainerEvent_CL
| limit 50

ContainerEvent_CL
| where Message contains "warn"

ContainerEvent_CL
| where Message contains "error"

ContainerEvent_CL
| where Message contains "stop"

ContainerEvent_CL
| where ContainerGroup_s == "acihealthprobecontainergroup"
| where Message contains "stop"
| where TimeGenerated > ago(3m)
```
Review log entries for warnings, errors, and stop events to assess container health.

## Conclusion
- Deployed and linked a Log Analytics Workspace
- Diagnosed and redeployed a faulty container
- Queried logs to monitor container behavior

---

# Lab Output Screenshots

![1](https://github.com/user-attachments/assets/ef597006-e7d6-4e47-9ff8-16a3e5803a82)
![2](https://github.com/user-attachments/assets/13872aa5-7bc3-497d-b7a0-9e4815f2a14f)
![3](https://github.com/user-attachments/assets/faf42368-967a-4230-b566-33265bcc0216)
![4](https://github.com/user-attachments/assets/60742788-7bb9-4833-b3c0-2e57d41324e1)
![5](https://github.com/user-attachments/assets/64a492e2-e5a5-4c10-bdbb-6c21364c9482)
![6](https://github.com/user-attachments/assets/4f6416e2-80fe-4879-9c71-4e85ed7e0a70)
![7](https://github.com/user-attachments/assets/2dc72afb-7dcd-4f8f-8f25-a6daa67ffcfb)
![8](https://github.com/user-attachments/assets/5e660de2-fd84-4371-8391-ba2a6a8944ac)
![9](https://github.com/user-attachments/assets/865753f3-a6d5-42aa-b341-1283d39dedd1)
![10](https://github.com/user-attachments/assets/56afdffb-8fc3-44f2-8874-cd3e853acd66)
![11](https://github.com/user-attachments/assets/761fd94c-b4cf-4f96-91fc-b43daea3eeab)
![12](https://github.com/user-attachments/assets/071280ca-7ac8-411d-b74b-97007d6be9d2)
![13](https://github.com/user-attachments/assets/89584020-00db-4289-82bf-a9aa1e83cd3f)
![14](https://github.com/user-attachments/assets/e50de25b-3b4e-4113-b3ae-b1bd8d14d606)
![15](https://github.com/user-attachments/assets/3719d3d3-0320-44fd-8197-906b2f5fce74)
![16](https://github.com/user-attachments/assets/b91038e4-904e-4f47-86ca-6e00f37bdf02)
![17](https://github.com/user-attachments/assets/1e9bbd41-fece-4fac-8a48-7444ad0332cc)
![18](https://github.com/user-attachments/assets/1094e1dc-2053-47fe-a324-2f439e1528b0)
![19](https://github.com/user-attachments/assets/ab4426ee-9a9b-4435-bb89-c1cffc37f6d4)
![20](https://github.com/user-attachments/assets/628b781c-1143-4eee-8f9d-5b80abfc694e)
![21](https://github.com/user-attachments/assets/685881e6-87f9-468f-9817-8ea1b2cfd6b7)
![22](https://github.com/user-attachments/assets/9dbbe1f6-cf31-4b09-a08c-dcf57eb01515)
![23](https://github.com/user-attachments/assets/84ad5fa8-e84e-4e0e-ac0d-c429f98419e1)
![24](https://github.com/user-attachments/assets/a3cf3ad2-c5e0-4f13-ade6-4fa6579e7d09)
![25](https://github.com/user-attachments/assets/db078eeb-a112-48ee-958d-5c884fdb9ff6)
![26](https://github.com/user-attachments/assets/d6024a03-631c-4f6e-a1bc-16468c3c93c7)
![27](https://github.com/user-attachments/assets/477f1b6a-013b-4538-b5e1-183d56a02813)
![28](https://github.com/user-attachments/assets/fed568f8-aca1-4b1a-9313-54655ed533ee)
![29](https://github.com/user-attachments/assets/a16b0669-6ea3-41a6-b558-dfde2e2c3bcc)
![30](https://github.com/user-attachments/assets/496b406c-2ebf-41b1-8e85-61b991039699)

