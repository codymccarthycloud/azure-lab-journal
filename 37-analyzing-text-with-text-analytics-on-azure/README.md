# Analyzing Text with Text Analytics on Azure

This guide walks you through the process of using Azure AI Language services to analyze sentiment, extract key phrases, and identify entities from sample reviews.

---

## Lab Steps

### 1. Log in & Examine Reviews
- Log into the Azure Portal using credentials provided
- Read sample reviews:
  - Review 1: Positive experience at a Chicago restaurant
  - Review 2: Negative experience with cold food and rude service

### 2. Open Azure Cloud Shell
- Click the terminal icon (top bar)
- Choose **Bash** environment

### 3. Clone Repo & Install Requirements
```bash
git clone https://github.com/pluralsight-cloud/ai-900-azure-ai-fundamentals-natural-language-processing-workloads.git
cd ai-900-azure-ai-fundamentals-natural-language-processing-workloads
pip install -r requirements.txt --user
```

### Add API Credentials
- Go to Azure AI Services → Keys and Endpoint
- Open 1-text-analysis.py in Cloud Shell editor
- Replace placeholder values in lines 13–14:

```python
endpoint = "YOUR_ENDPOINT"
key = "YOUR_KEY"
```

### Run the Text Analysis App

```python
python 1-text-analysis.py
```

Press Enter to progress through:
- Sentiment analysis
- Key phrase extraction
- Entity recognition
- Analysis of second review

---

## Labout Output Screenshots

![1 git clone download the github folders and files cd to the folder](https://github.com/user-attachments/assets/bd2526ee-c966-4e3d-89db-d4dc638cf05b)
![2 pip install user r requirements txt download](https://github.com/user-attachments/assets/4bca23ba-0e0a-4b2b-b158-29b1d66efa73)
![3 install the requirements txt and switch to the editor in powershell](https://github.com/user-attachments/assets/55bae039-2ee8-4883-850f-f37319837461)
![4 powershell cli switch from bash to the editor open the py file downloaded naviagte to azure ai services keys and endpoints](https://github.com/user-attachments/assets/c674922e-fdc5-4575-bf7b-4c9111851627)
![5 copy key and endpoint into the py script using the powershell editor](https://github.com/user-attachments/assets/8af847d2-691b-4ef1-b49e-ecacbcc47a7b)
![6 save the py file](https://github.com/user-attachments/assets/c3957ec9-1e44-4ab9-a95a-91b497d80c2f)
![7 running the python file analyzing text using ai text anayltics](https://github.com/user-attachments/assets/07640b83-7035-40cb-ba45-8c049195d1bd)
![8 second analysis negitive review sentiiment analysis key phrases entities datetime product](https://github.com/user-attachments/assets/3f7be4f6-1505-4bc6-9da8-d93d6c98921b)



