# Creating a Clustering Model with Azure ML Designer
Data scientist at The Greenery, a gardening store. After Steve the intern spilled all the seeds on the floor, 
you’ve been asked to build a clustering model to group seeds by their features before the boss finds out.

### Learning Objectives
- Create a dataset in Azure ML Studio using seed data
- Build a clustering pipeline using drag-and-drop modules
- Normalize and split data
- Train a K-Means clustering model
- Assign data to clusters and evaluate results


## Create the Seeds Dataset
Go to Azure ML Studio > Data > Create

Name: Seeds
Type: Tabular (Azure ML v1 APIs)
Source: From web files
URL:

Code
https://raw.githubusercontent.com/MicrosoftDocs/ml-basics/master/data/seeds.csv
Review schema → Click Create

## Build the Clustering Pipeline
Modules & Configuration

Module                     | Configuration Notes
---------------------------|----------------------------------------------------
Seeds Dataset              | Drag onto canvas
Normalize Data             | Exclude 'species' column
Split Data                 | Set fraction to 0.7 for training / 0.3 for testing
K-Means Clustering         | Use default settings
Train Clustering Model     | Input: normalized training data
Assign Data to Clusters    | Input: trained model + testing data
Evaluate Model             | Input: clustered data


3. Run and Submit Pipeline
- Click Configure & Submit
- Create new experiment: seeds
- Compute target: Compute cluster
- Submit and monitor job progress under Jobs

## Preview Evaluation Results
Once completed, right-click Evaluate Model > Preview Data
Review clustering performance and assigned groups

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/ff9e1e28-39af-43a7-aa7c-822592616ec1)
![2](https://github.com/user-attachments/assets/825d1bd4-57bb-4ce5-b198-4426c27462b4)
![3](https://github.com/user-attachments/assets/38d82d68-7bc7-4d91-9bc3-93efa2492746)
![4](https://github.com/user-attachments/assets/d0994f2b-cec4-4920-9ecb-ae29974210a7)
![5](https://github.com/user-attachments/assets/a2e154a7-b86e-4c23-afd0-6bebe3c3d30c)
![6](https://github.com/user-attachments/assets/ebda7b5a-5ef3-4f45-b0ec-e08ee6c40b74)
![7](https://github.com/user-attachments/assets/831dc698-8462-4df3-81a7-328624bee3d0)
![8](https://github.com/user-attachments/assets/41c42a9a-6df3-430d-84e3-162bdc4c4995)
![9](https://github.com/user-attachments/assets/cd787caf-a43f-4a9a-ab6a-da9ff1f20af1)
![10](https://github.com/user-attachments/assets/d2965652-4abe-4b1b-bd30-0f8d36201ea7)
![11](https://github.com/user-attachments/assets/0b70cda8-a6f6-4a49-b845-f81348ab878d)
![12](https://github.com/user-attachments/assets/3137e4ad-80c6-49fb-879d-cf2dd81a3e08)
![13](https://github.com/user-attachments/assets/2f500a85-f488-4a79-98d9-971b5aa5590f)
![14](https://github.com/user-attachments/assets/9660cc02-a9e3-4dba-83c7-9d58499e0015)
![15](https://github.com/user-attachments/assets/18806607-7db6-442e-92f8-5e0739a776e0)
![16](https://github.com/user-attachments/assets/9461a554-67c0-4966-adea-0810c5605a59)
![17](https://github.com/user-attachments/assets/69066571-9fce-4c86-829a-d6135c2c7e18)
![18](https://github.com/user-attachments/assets/c08acf9a-3aa5-4121-9a51-b7632073a62b)
![19](https://github.com/user-attachments/assets/208e762d-dd78-4e9c-a92b-d8b45120ff06)
![20](https://github.com/user-attachments/assets/08b74eef-5cc6-4111-9e9d-4d407a7ecb24)
![21](https://github.com/user-attachments/assets/ca1bad8d-26d6-4c9f-8b2c-47bbc168a720)
![22](https://github.com/user-attachments/assets/450d6c6c-160e-422e-a515-6dc2a96932b9)
![23](https://github.com/user-attachments/assets/5a378536-d995-4ff0-9116-996744a96952)
![24](https://github.com/user-attachments/assets/d3b9d094-39fa-476e-b955-302fc42cad82)
![25](https://github.com/user-attachments/assets/077b4a3e-3bf6-4c8c-a8f7-56c7e7f3f91e)
![26](https://github.com/user-attachments/assets/d8eba09e-0945-4f75-8e06-24e2bc7e1029)
![27](https://github.com/user-attachments/assets/9bb8c6b1-2ee9-4257-aa70-47e666d5c29e)



