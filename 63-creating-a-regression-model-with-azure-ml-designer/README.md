# Creating a Regression Model with Azure ML Designer

### Scenario
You're a data scientist at Bike4Ever, a bike rental company. Your task is to build a regression model that predicts bike rentals based on features like weather, temperature, and day of the week.

## Set Up Azure ML Studio
Log in to the Azure portal using lab credentials.
Launch Azure Machine Learning Studio from your workspace.

## Create and Upload Dataset
Download the dataset: Microsoft bike rental data
In Azure ML Studio:
- Go to Data → Click +Create
- Name: bikerentals
- Type: Tabular (Azure ML v1 APIs)
Source: From web files
- Upload the CSV file
- Review schema → Click Create

## Build the Training Pipeline

Modules & Configuration

Below is a summary of the modules used in Azure ML Designer and their configuration notes:

```
| Module                       | Configuration Notes                            |
|------------------------------|-------------------------------------------------|
| bikerentals                  | Drag onto canvas                                |
| Select Columns in Dataset    | Exclude `year` column                           |
| Clean Missing Data           | Remove entire row                               |
| Split Data                   | 70% training / 30% testing (0.7)                |
| Linear Regression            | Use default settings                            |
| Train Model                  | Label column: `rentals`                         |
| Score Model                  | Connect trained model and test data             |
| Evaluate Model               | View RMSE and R² (Coefficient of Determination) |
```

## Run and Evaluate
- Click Configure & Submit
- Create experiment: bikerentals
- Select compute target: Compute cluster
- After completion, right-click Evaluate Model → Preview Data

## Review Evaluation Model Results in Jobs
Look for:
- Root Mean Squared Error (RMSE): Lower is better
- R² Score: Closer to 1 means better fit

### Conclusion
- Clean data before training to avoid skewed results.
- Exclude irrelevant columns like year to improve model accuracy.
- Use RMSE and R² to compare different regression models.

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/beea7a03-9d73-4805-899b-f007ed8d708b)
![2](https://github.com/user-attachments/assets/c017468d-501c-4b0c-8467-8bf565801704)
![3](https://github.com/user-attachments/assets/87fc7ab6-2fa7-4064-8b51-2a7a9dd2b269)
![4](https://github.com/user-attachments/assets/856da5c4-5118-4114-9b23-ff8de8dde7cc)
![5](https://github.com/user-attachments/assets/a1d08371-754e-4b15-a177-cada880c421a)
![6](https://github.com/user-attachments/assets/5dd79899-f842-42f0-9e0e-076ead70ea88)
![7](https://github.com/user-attachments/assets/8728fcbc-35d6-4bf1-bd26-7a5d618c180c)
![8](https://github.com/user-attachments/assets/4f2b559c-94c1-4182-8139-85fac2c77b2c)
![9](https://github.com/user-attachments/assets/491ccbe9-2287-4dfc-b676-8cbf60ae7c56)
![10](https://github.com/user-attachments/assets/6f18438d-be94-4268-9892-20dfeb243458)
![11](https://github.com/user-attachments/assets/9efb74f1-f6f7-4b28-bdbf-1167d825f7fb)
![12](https://github.com/user-attachments/assets/2892a8a6-edbd-43c8-83b9-90ffcde2ca3d)
![13](https://github.com/user-attachments/assets/a896d34c-4601-4e05-a1aa-a248a7283ae3)
![14](https://github.com/user-attachments/assets/f4fea6d9-7c4d-4532-b487-c2e853a4ee7c)
![15](https://github.com/user-attachments/assets/d1269e7c-707f-4d47-90ac-4a8d98e6fb84)
![16](https://github.com/user-attachments/assets/bff37f71-013a-4178-816c-97bf50d27d7d)
![17](https://github.com/user-attachments/assets/3682d3f9-e2e7-45ee-93f3-2970d716313b)
![18](https://github.com/user-attachments/assets/9aa97876-523c-412e-9d4e-d6b279cedf16)
![19](https://github.com/user-attachments/assets/696f8949-bbc7-484f-a24d-c94950a5b4b9)
![20](https://github.com/user-attachments/assets/8c109e9e-2891-48bf-87bd-fea1d42c0ab1)
![21](https://github.com/user-attachments/assets/bee5b5cb-7c58-4c5e-bb66-ed2eaa43dc08)
![22](https://github.com/user-attachments/assets/8430f52c-a9d4-4b27-bb66-9145c9030cb5)
![23](https://github.com/user-attachments/assets/b376dd24-dacf-4150-83ad-6e80c400cad4)
![24](https://github.com/user-attachments/assets/8900d6b4-a7e0-4a13-86ac-902758d63457)
![25](https://github.com/user-attachments/assets/9fec234b-b5d3-4d97-a0fe-62c9e6bc97fb)
![26](https://github.com/user-attachments/assets/4b501da2-bd41-4094-a866-eda658fd41ea)
![27](https://github.com/user-attachments/assets/7c2d3cc3-39d9-4688-8d55-70bb5960bf24)
![28](https://github.com/user-attachments/assets/cbd41f79-9598-4f56-ab0c-d49794d40f88)

