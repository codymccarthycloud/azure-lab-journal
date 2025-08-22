# Creating a Classification Model with Azure ML Designer

### Overview
You're a data scientist at AIDoctor, tasked with predicting whether a patient is diabetic based on features like age, blood pressure, and BMI.

## Create and Upload Dataset

- Launch the Azure Machine Learning Studio from your workspace
- Go to the Data tab.
- Click Create → Name: Diabetes
- Type: Tabular (Azure ML v1 APIs)
- Source: From web files
URL:
Code
https://raw.githubusercontent.com/MicrosoftLearning/mslearn-azure-ml/main/Labs/03/data/diabetes.csv
Review and confirm schema > Click Create

## Build the Training Pipeline
Go to Designer > Create a new pipeline

Drag and drop modules in this order:
Modules & Configuration


| Module                        | Configuration Notes                    |
--------------------------------|-----------------------------------------
| Diabetes Dataset              | Drag onto canvas                       |
| Select Columns in Dataset     | Exclude 'PatientID'                    |
| Normalize Data                | Exclude 'Diabetic'                     |
| Split Data                    | Set split to 70% training / 30% test   |
| Two-Class Logistic Regression | Use default settings                   |
| Train Model                   | Label column: 'Diabetic'               |
| Score Model                   | Connect trained model and test data    |
| Evaluate Model                | View accuracy, precision, recall       |
--------------------------------------------------------------------------


## Run and Evaluate

- Click Configure & Submit
- Create experiment: diabetesJob
- Select compute target: Compute cluster
- After completion, right-click Evaluate Model > Preview Data

## Create Inference Pipeline
Click Create inference pipeline → Real-time inference

Add:
- Web Service Input
- Web Service Output
- Remove Evaluate Model
- Connect modules accordingly
- Submit the pipeline again under the same experiment

## Deploy as Real-Time Endpoint

- After successful run, click Deploy
- Choose compute target: ACI (for testing) or AKS (for production)
- Once deployed, access via Endpoints tab

### Insights

- Adjust threshold to balance precision vs. recall
- Use confusion matrix to interpret model performance
- Monitor endpoint usage and latency under Monitoring

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/106ca21f-4cb1-4e5f-b593-d9f086c11c67)
![2](https://github.com/user-attachments/assets/e313a2ef-7ff6-48db-9821-18784505e292)
![3](https://github.com/user-attachments/assets/71820711-552b-4e1a-ba3c-2800c6dd03cf)
![4](https://github.com/user-attachments/assets/b90c019d-f565-475d-bbc2-455ae87b7752)
![5](https://github.com/user-attachments/assets/5cd35dc3-b29a-4956-8322-4188708154ca)
![6](https://github.com/user-attachments/assets/d51ed783-a389-4b46-bf8c-1d4b96c5d03a)
![7](https://github.com/user-attachments/assets/cca3b6b8-657d-4d98-bfc4-3b24c4249669)
![8](https://github.com/user-attachments/assets/b81a2be3-b926-4b8d-bf0a-9b2dee21c337)
![9](https://github.com/user-attachments/assets/89353677-4509-4a03-8060-2a8d57551674)
![10](https://github.com/user-attachments/assets/cd7c0076-cff9-4817-b8d1-8e37cb94791f)
![11](https://github.com/user-attachments/assets/8b5a0f2c-7944-4d37-ac36-e04abc7b6af1)
![12](https://github.com/user-attachments/assets/75c3e673-2fe0-4b73-b6a7-6e883eeca88e)
![13](https://github.com/user-attachments/assets/74768836-4659-41a2-b0e3-56e6b24f388a)
![14](https://github.com/user-attachments/assets/4d73a0e0-023f-4fb0-aee6-f6d58c9eccc1)
![15](https://github.com/user-attachments/assets/4c319a27-7891-46d0-a5fc-8ecebfef5999)
![16](https://github.com/user-attachments/assets/d29c0f6b-edac-41f5-a36a-0b375e3a0d6a)
![17](https://github.com/user-attachments/assets/9c6c1de7-c0e3-46fa-bd1a-1abadadf2103)
![18](https://github.com/user-attachments/assets/f355de58-37fa-476a-a40e-a7603abc16af)
![19](https://github.com/user-attachments/assets/517abdfb-8cbb-4e77-844e-8a40b377e19b)
![20](https://github.com/user-attachments/assets/d9cfd5fb-fb0e-4b4b-86d1-b33edd33bc6b)
![21](https://github.com/user-attachments/assets/f0fe5f5a-5fe2-43ba-8722-c7624894b71b)
![22](https://github.com/user-attachments/assets/cbaf6f32-aa5c-4a86-ba5b-f8bb3eb47122)
![23](https://github.com/user-attachments/assets/d683c41b-cec1-4677-bc8b-b28d7f5a4761)
![24](https://github.com/user-attachments/assets/1369759e-52de-4fe9-82ea-ce9fc0726164)
![25](https://github.com/user-attachments/assets/3dfb9688-e0cf-4443-8c4a-ad140bf02934)
![26](https://github.com/user-attachments/assets/aa5c649b-b06c-45e0-9eb0-e303d0d764a5)
![27](https://github.com/user-attachments/assets/1b46f577-eff1-4de5-90eb-93ddbebd9c1f)
![28](https://github.com/user-attachments/assets/36dbb0eb-a72d-4f4e-9e0a-8925d9b123ad)
![29](https://github.com/user-attachments/assets/18b02aa3-a049-4c5d-b365-2b11825a87b0)
![30](https://github.com/user-attachments/assets/7234f912-4231-4933-bc0d-fa78ee78f707)
![31](https://github.com/user-attachments/assets/df64be73-782c-49a7-b7a5-28c970edc36b)
![32](https://github.com/user-attachments/assets/363ef545-3731-433d-824f-beae0a0d8425)
![33](https://github.com/user-attachments/assets/bae50477-a725-40e8-b391-d0f961c653b3)
![34](https://github.com/user-attachments/assets/049b39aa-2bd2-4546-b63f-60aac4b6d6cf)
![35](https://github.com/user-attachments/assets/323eeaad-c7e2-4c66-ad72-e3391a52ae78)
![36](https://github.com/user-attachments/assets/1c83db78-ea9b-4ba8-a9ad-c0c6b2b5d01b)
![37](https://github.com/user-attachments/assets/ade8ddd2-83d9-4f76-9c99-a3f1c2432211)
![38](https://github.com/user-attachments/assets/7f2731e7-d0a3-4694-9a6c-71d021a9e649)
![39](https://github.com/user-attachments/assets/2d950211-5cb5-4321-bc4b-ead9b747fd6e)
![40](https://github.com/user-attachments/assets/a764231d-b5ae-4c45-9ac7-0b14b37ea162)
![41](https://github.com/user-attachments/assets/c4562a45-06ba-485d-8209-88c210815962)
![42](https://github.com/user-attachments/assets/61f2cdd7-6398-4081-bd2b-5ac567182357)
![43](https://github.com/user-attachments/assets/8914050c-8e89-45bc-95cc-7f811866cbc0)
![44](https://github.com/user-attachments/assets/09b94a1a-b1f7-493f-8fb0-333e53ede97c)
![45](https://github.com/user-attachments/assets/ec08e78f-62b1-4536-9ade-5c5c639ead4e)
![46](https://github.com/user-attachments/assets/087f5eee-5b85-48c9-9c71-b6d4cc793803)
![47](https://github.com/user-attachments/assets/14ad2e8f-2824-47d4-8b13-f0e1b6cd82c6)
![48](https://github.com/user-attachments/assets/33f07fc3-0251-486e-a2cf-37b80a17772b)
![49](https://github.com/user-attachments/assets/4931d802-c1e1-4167-b2ad-4fa7a15d3ad4)
![50](https://github.com/user-attachments/assets/60138caa-f721-42fb-be38-fc7a7212697f)
![51](https://github.com/user-attachments/assets/bc9101c6-806f-4eb3-9589-04aece2363b7)
![52](https://github.com/user-attachments/assets/64e02459-f4c2-4e50-a24d-7fcd6183cc97)
![53](https://github.com/user-attachments/assets/f1c5f0b6-6881-40fc-995a-bd23a831eb32)
