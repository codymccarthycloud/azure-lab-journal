# Object Detection with Azure Custom Vision

## Step 1: Download Training and Testing Images
- Navigate to the [Azure Lab Journal GitHub repo]
- Locate the folders for **training-images** and **testing-images**.
- Download each as a ZIP by clicking **Code > Download ZIP** or using the GitHub CLI.
- Unzip locally and review contents.

---

## Step 2: Train the Custom Vision Model
1. Go to [Azure Custom Vision Portal](https://customvision.ai/).
2. Sign in and select **Projects > New Project**.
3. Name your project and select:
   - **Project Type:** Object Detection
   - **Domain:** Retail, General, or Compact depending on use case.

---

## Step 3: Upload & Tag Training Images
- Click **Add Images** and upload your unzipped training folder.
- Use the **bounding box tool** to tag objects in each image.
- Assign appropriate tags (e.g., `cat`, `dog`, `person`, etc.).
- Save each image after tagging.

---

## Step 4: Train the Model
- Click the **Train** button in the top-right.
- Select **Quick Training**.
- Wait for the model to finish training; status will change to “Trained”.

---

## Step 5: Run Testing Images
- Click **Quick Test** in the model dashboard.
- Upload your unzipped testing images.
- View detection results with predicted objects and confidence scores.

---

## Step 6: Adjust Thresholds
- Navigate to the **Performance tab**.
- Tune the **Probability Threshold** slider to reduce false positives.
- Retest using key test images to observe improvements.

---

## Step 7: Test and Evaluate
- Review precision, recall, and mean average precision (mAP).
- Export model to TensorFlow, CoreML, ONNX, etc. if needed.

---

## Additional Tips
- Use meaningful tags for training consistency.
- Ensure balanced image counts across all object categories.
- Improve model by uploading more varied and high-quality samples.

---

## Lab Output Screenshots

![1 navigate to ai foundry more services custom vision](https://github.com/user-attachments/assets/6873b12d-89ae-418f-a298-6c3d505eee95)
![2 login to the custom vision ai webpage](https://github.com/user-attachments/assets/9a8c570a-cc18-4667-b992-bfc0ba50ad38)
![3 create new project in custom vision ai food detection project types object detection](https://github.com/user-attachments/assets/b47136da-96c2-4510-90ed-e7b2b5c6abbb)
![4 upload training images to custom vision ai](https://github.com/user-attachments/assets/c9fe914f-7ba4-4ca4-aaca-dfa60659346c)
![5 tagging bell pepper](https://github.com/user-attachments/assets/41f6759e-a412-4ec8-9ee4-f452bcd1241f)
![6 train after tagging bell peppers and carrots](https://github.com/user-attachments/assets/aaa20aa2-6c9d-4434-944d-49785ae01b6b)
![7 training](https://github.com/user-attachments/assets/3e24005a-b24f-48fc-9195-728a7a8d107b)
![8 training complete](https://github.com/user-attachments/assets/81f39988-dfbc-4a98-af81-a4e72f13e55b)
![9 quick test increase threshold value 91%](https://github.com/user-attachments/assets/d997b70f-1a49-45b6-8ab9-16ab4c1a8703)
![9 quick test threshold for carrot analysis](https://github.com/user-attachments/assets/fcabffbd-0823-44b8-b2b5-3a850edc1e92)






