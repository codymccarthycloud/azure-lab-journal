# AI-900 Image Analysis Lab – Azure Cognitive Services

## Repo Structure Overview

```plaintext
AI-900-Artificial-Intelligence-Workloads-and-Considerations/
├── 1-image-analysis.py
├── 2-face-analysis.py
├── requirements.txt
└── images/
    ├── image-analysis/
    │   ├── 1-computervision-couple.jpg
    │   ├── 2-azureface-couple.jpg
    ├── image-classification/
    │   └── Landmarks.zip
    └── object-detection/
        └── Foods.zip
```

---

## Lab Setup

### 1. Clone the Lab Repo

https://github.com/pluralsight-cloud/AI-900-Artificial-Intelligence-Workloads-and-Considerations/tree/main

```bash
git clone https://github.com/pluralsight-cloud/AI-900-Artificial-Intelligence-Workloads-and-Considerations.git
cd AI-900-Artificial-Intelligence-Workloads-and-Considerations
```

### 2. Install Required Packages

Use this to install all dependencies:

```bash
pip install --user -r requirements.txt
```

Or manually install key modules:

```bash
pip install --user azure-cognitiveservices-vision-computervision msrest
```

---

## Configure Credentials

Open the `1-image-analysis.py` file with:

```bash
nano 1-image-analysis.py
```

Then replace the placeholders:

```python
subscription_key = "your_azure_key"
endpoint = "https://your-region.api.cognitive.microsoft.com/"
```

Save the file (`Ctrl + O`, then `Enter`, then `Ctrl + X`).

---

## Run the Image Analysis Script

```bash
python3 1-image-analysis.py
```

If successful, it returns descriptions or tags for the image in `images/image-analysis/1-computervision-couple.jpg`.

---

## Troubleshooting Tips

- `ModuleNotFoundError`: Run `pip install --user azure-cognitiveservices-vision-computervision`
- `KeyError: 'Endpoint'`: Ensure you're not referencing `os.environ['Endpoint']` unless you've set that env var
- GUI editor (`{}`) not showing? Use `nano` or `code` instead inside Cloud Shell

---

## Related Files

- `requirements.txt` – Package list for installation
- `2-face-analysis.py` – Facial recognition example
- `images/` – Test images and zipped assets for various exercises

---

## Completion

Once you’ve:
- Edited `1-image-analysis.py`
- Installed dependencies
- Run the script and reviewed results

---

## Lab Output Screenshots

![git clone](https://github.com/user-attachments/assets/7ad9b839-8830-40b4-915f-56bdb028799a)
![git clone then cd AI tab](https://github.com/user-attachments/assets/85147fc3-2cb5-4bc4-a7c9-a7d9ff15c6d8)
![pip install -r requirementsdottxt](https://github.com/user-attachments/assets/6455aeeb-d9e2-40f5-8109-4216c4226a92)
![paste key and endpoint into 1-image-analysis](https://github.com/user-attachments/assets/bbb5c063-8a08-49d5-8907-33bc4482d34b)
![python 1-image-analysis py](https://github.com/user-attachments/assets/adfcc5a6-a714-450b-acde-a209e80588aa)
![enter to continue to face detection](https://github.com/user-attachments/assets/43aa00e5-a8df-4025-b7b3-41c1cfe1bb31)




