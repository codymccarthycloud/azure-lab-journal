# Using Azure Automated ML – Summary Lab Guide

---

## Lab Goals

- Create an Azure ML Studio workspace and dataset
- Run an automated ML experiment
- Review model metrics
- Deploy the trained model
- Test the model with sample input

---

## Learning Objectives & Steps

### 1. Create Dataset in Azure ML Studio
- Use the taxi fare prediction dataset from Microsoft.
- Load data into a **new dataset** in ML Studio.
-  Mark as complete once created.

---

### 2. Configure and Start Automated ML Run
- Set timeout settings:
  - Expand limits → set **Experiment timeout** to **15 minutes**
- Launch the AutoML experiment.
-  Mark as complete after run starts.

---

### 3. Review Results
- Inspect key metrics:
  - R² score
  - Root Mean Squared Error
- Identify the best-performing model candidate.
-  Mark as complete after analysis.

---

### 4. Deploy Model to Real-Time Endpoint
- Set up model deployment:
  - Virtual machine size: `DS2_v2`
  - Instance count: `1`
- Deploy using Azure ML Studio portal.
-  Mark as complete after deployment.

---

### 5. Test Your Model
- Use test input JSON:

```json
{
  "input_data": {
    "data": [
      {
        "vendor_id": "CMT",
        "rate_code": 1,
        "passenger_count": 1,
        "trip_time_in_secs": 1271,
        "trip_distance": 3.8,
        "payment_type": "CRD"
      }
    ]
  }
}
```

- Compare prediction to actual fare: `17`
-  Mark as complete after test run.

---

## Tips
- Open lab in **incognito mode** for best results.
- Use Azure CLI to manage stuck workspaces if needed:
  ```bash
  az ml workspace list-deleted
  az ml workspace purge --name <workspace-name> --location <region>
  ```

---

## Lab Output Screenshots

![azure amchine learning workspace launch studio](https://github.com/user-attachments/assets/aa24f06b-d2b2-4337-9009-6dd6742707ff)
![azure ai machine learning studio navigate to automated ml](https://github.com/user-attachments/assets/75dab533-1702-44e2-a597-a3a6241a96b4)
![choose from web files](https://github.com/user-attachments/assets/24a16377-fc2d-483c-abd3-ec4ed04b9004)
![create data asset as tabular for taxifare url](https://github.com/user-attachments/assets/5174d338-36a2-43e4-a373-37fee32d2f6a)
![retrieve data from public webpage url]
![schema select what values to display](https://github.com/user-attachments/assets/37b370e1-b897-4116-8a1d-1a380f776f7f)
![create dataset](https://github.com/user-attachments/assets/d01e4761-5a5f-4453-b457-50011b702b9e)
![deploy vm DS2_v2 taxifares](https://github.com/user-attachments/assets/f60d745b-df08-4585-9a9f-eb521edc20e4)
![machine learning studio ai model](https://github.com/user-attachments/assets/c33f8014-6ad8-4d3c-8f8b-6f3b254eb543)
![model predicted value](https://github.com/user-attachments/assets/8137a3e9-67bc-43d3-adc3-4e8a479c578b)
![deploy to real time endpoint](https://github.com/user-attachments/assets/bafec124-db03-4903-93c0-3aa65592c45a)
![test](https://github.com/user-attachments/assets/8bd0078e-6f27-4056-a37e-22b9b007d9f5)




