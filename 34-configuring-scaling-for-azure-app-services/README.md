# Configuring Scaling for Azure App Service

---

## Objectives

- Sign in to Azure Portal with lab credentials
- Configure custom autoscaling for App Service Plan
- Deploy a sample Flask app from GitHub
- Observe instance count behavior after deployment

---

## Steps

### Access Azure Portal

- Locate the App Service and its associated App Service Plan on Azure

---

### Set Up Autoscaling

#### Autoscale Settings

- **Minimum instance**: 1  
- **Maximum instance**: 2  
- **Default instance**: 1  

#### Rule Configuration

| Metric Trigger         | Action              |
|------------------------|---------------------|
| CPU ≥ 60% (Maximum)    | Increase by 1       |
| CPU ≤ 30% (Average)    | Decrease by 1       |

You’re using **Scale based on a metric**, so the "scale to specific instance count" option is disabled by default.

---

### Deploy Test App

- Use Deployment Center and GitHub integration
- Sample Repo: [Azure-Samples/msdocs-python-flask-webapp-quickstart](https://github.com/Azure-Samples/msdocs-python-flask-webapp-quickstart)
```bash
git clone https://github.com/Azure-Samples/msdocs-python-flask-webapp-quickstart.git
```

---

### Monitor Instance Behavior

After deploying:
- Azure won’t scale out unless CPU threshold is triggered
- Deployment alone doesn't count as “load”
- Use Azure metrics to observe CPU usage
- Instance count may remain at default due to low demand
- Confirm autoscale rules are active

### Observations

- Autoscale rules configured correctly
- Instance count remained stable post-deploy (expected due to low CPU load)
- Scaling settings now in place for traffic-based activation

### Next Steps

- Load-test app to simulate real scaling conditions
- Tune cooldown settings if needed
- Consider increasing max instances for larger traffic spikes

---

## Lab Output Screenshots

![1 web app scale out scale out method rules based](https://github.com/user-attachments/assets/2c4ccb5d-004e-4846-9e80-3602b87aa43e)
![2 create autoscale setting outbound scale rule time aggregation maximum check for cpu spike last 5 minutes](https://github.com/user-attachments/assets/f6aa388e-4d8c-4938-8db0-68aa1e912a59)
![3 rules applied save austoscale settings](https://github.com/user-attachments/assets/906a3f42-8165-4cf0-b830-fd183122c5b2)
![4 go back one page to scale out in web app settings and click configure](https://github.com/user-attachments/assets/2eb12826-ad78-46ae-bf06-0ca3f6fb2f26)
![5 web app deployment center to measure cpu for auto scaling](https://github.com/user-attachments/assets/28867d0b-26a4-40fa-a7a2-ad3840c04f13)
![6 deployment center git hub connected cpu is running](https://github.com/user-attachments/assets/2b5596ff-fab6-4737-a7bc-943f8b2710fe)








