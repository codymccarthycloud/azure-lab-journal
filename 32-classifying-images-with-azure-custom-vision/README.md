# Classifying Images with Azure Custom Vision

This lab walks you through the process of using Azure's Custom Vision service to train a model 
that can classify images of landmarks as either the **Golden Gate Bridge** or the **Statue of Liberty**.

## Learning Objectives
- Log into the Azure and Custom Vision portals
- Download and prepare image datasets
- Create and train a classification project
- Test image predictions using Quick Test

## Step-by-Step Instructions

### 1. Log In to Azure & Custom Vision
- Use the lab credentials provided
- Open portals in **incognito** mode:
  - Azure Portal: `https://portal.azure.com`
  - Custom Vision Portal: `https://customvision.ai`

### 2. Prepare Your Dataset
- Download `Landmarks.zip` from GitHub (linked in lab)
- Extract images locally
- Split into:
  - `Training Images` folder
  - `Testing Images` folder

### 3. Create the Classification Project
- In the Custom Vision portal:
  - Select **Classification (Multiclass - Single tag per image)**
  - Choose the **Landmarks** domain
  - Upload training images
  - Tag as `Golden Gate Bridge` or `Statue of Liberty`
  - Train using **Quick Training**

### 4. Run Image Tests
- Use the **Quick Test** feature
- Upload images from the testing folder
- Confirm label predictions

## Completion Checklist
- Accessed both Azure portals
- Downloaded and extracted images
- Created and trained classification model
- Verified predictions via Quick Test

---

## Lab Output Screenshots

![1 download zip from github url and unzip](https://github.com/user-attachments/assets/43ae2018-8fa3-418e-80bc-e52a4d6ca307)
![2 customvision ai portal upload training images with single tag setting for landmark classification](https://github.com/user-attachments/assets/537bc09e-a37c-47e3-9fd1-9c2fe948387d)
![3 quick training](https://github.com/user-attachments/assets/a9053a19-537e-4ed0-838a-090e0cf4ef2b)
![4 training finished](https://github.com/user-attachments/assets/4daa1014-fd6d-4b6e-ae50-1cfff2fa6ad6)
![5 quick test with testing images](https://github.com/user-attachments/assets/47ae197f-5dad-4352-a712-d8994bdfb233)
![6 quick test with testing image](https://github.com/user-attachments/assets/ed59cfdf-f500-42fd-94b7-bec691e566ad)







