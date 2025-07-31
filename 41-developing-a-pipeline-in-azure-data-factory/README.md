# Developing a Pipeline in Azure Data Factory

This lab guides you through creating a pipeline using Azure Data Factory to integrate and transform sales and parking lot data. 
It includes provisioning resources, building data movement, and combining datasets via data flows.

---

## Lab Steps

### 1. Prepare the Environment

Provision the following in Azure:

- **Data Factory (V2)**  
  - Region: West US 2  
  - Git integration: Optional (configure later)

- **Azure SQL Database**  
  - Region: East US  
  - Basic tier: 5 DTUs, 2 GB  
  - Includes table: `SalesLT.Address`

- **Storage Account**  
  - Region: West US 2  
  - Type: Standard Storage V2  
  - Redundancy: RA-GRS  
  - Containers: `raw`, `curated`

---

### 2. Create & Connect Datasets

- Link the SQL database and access the `SalesLT.Address` table.
- Upload an external CSV (parking lot data) to the `raw` blob container.
- Create a `curated` blob container.
- Define datasets for both SQL and CSV sources.

---

### 3. Build Copy Pipeline

- Use **Copy Data Activity** to pull data from SQL into Blob (`raw`).
- Validate the pipeline and execute the run.

---

### 4. Merge Datasets via Data Flow

- Create a **Data Flow**:
  - Input: SQL output & uploaded CSV
  - Transformation: Merge logic
  - Output: Combined file into `curated` container

---

### 5. Publish the Pipeline

- Merge pipeline and dataflow on completion.
- Run validation and debugger check debugger in monitor.
- Click **Publish All** to deploy changes.
- Verify successful pipeline run in Monitor tab.

---

## Insights

Understanding pipeline components improves your ability to automate data integration:

- Pipelines allow sequential data tasks across cloud services.
- Copy Data handles ingestion, while Data Flow enables transformation.
- Blob containers organize data by raw input and curated output.

>  You can add resource locks to prevent modification to critical components (e.g. `prod-datafactory-dlock`).

---

## Completion Checklist

| Task                              | Status     |
|-----------------------------------|------------|
| Data Factory provisioned          |  Done      |
| SQL + Storage created             |  Done      |
| CSV uploaded and dataset linked   |  Done      |
| Copy and Data Flow configured     |  Done      |
| Pipeline published and executed   |  Done      |

---

##  Lab Output Screenshots

![1 create a data factory](https://github.com/user-attachments/assets/b91cb531-af8f-4a6d-981d-eab1541d2c3f)
![2 create a data factory](https://github.com/user-attachments/assets/70459892-7b8c-4041-b307-c0a723f12fc8)
![4 create sql database server](https://github.com/user-attachments/assets/1ec5aa17-1cf1-42fc-8305-81398716227c)
![3 create sql database](https://github.com/user-attachments/assets/b1f64cad-f646-4a80-9c4a-2ef09b045d37)
![5 create sql database networking](https://github.com/user-attachments/assets/f517bdeb-eabe-41a8-98ab-5651f134845b)
![6 create sql database select sample database](https://github.com/user-attachments/assets/6d01fc53-cba8-4224-8219-71f9b6297c73)
![7 create storage account](https://github.com/user-attachments/assets/1afa06bb-54b8-4016-ac3a-04e59400a8e1)
![8 check notifications for deployments](https://github.com/user-attachments/assets/3f0ae9ff-2d95-4d99-a622-67a4aa6c6db3)
![9 create container zones raw](https://github.com/user-attachments/assets/9944b3ad-92d1-4bcb-b6d8-fd47be5370b8)
![10 container zones](https://github.com/user-attachments/assets/2a807469-56d3-4337-a577-5a43392d1102)
![11 launch data studio studio](https://github.com/user-attachments/assets/2af4e121-e9b9-4bae-9900-b2d5c0e5a822)
![12 launch data factory create pipeline](https://github.com/user-attachments/assets/7aa82d24-06de-4121-84a1-d9d0c1c78391)
![13 create dataset with azure sql database](https://github.com/user-attachments/assets/2c53c3d6-5b0b-4295-860a-df63851ff49d)
![14 database test connection](https://github.com/user-attachments/assets/e67ca32f-1f57-4a00-8ce6-8f111700b539)
![15 database dataset properties](https://github.com/user-attachments/assets/ed5be51d-5ca7-4682-897c-1f1cb46427c3)
![16 preview data](https://github.com/user-attachments/assets/6602de2b-c59e-4a1d-ad85-8da71488ffe6)
![17 connect blob storage pull data in and rewriting data back in blob storage account](https://github.com/user-attachments/assets/c85fac49-3bdc-435e-a881-94f12b43956a)
![18 azure storage blob create](https://github.com/user-attachments/assets/610da70e-84d9-4d30-bbca-0631dc830539)
![19 connect raw](https://github.com/user-attachments/assets/200faed2-7b5d-47bb-964b-3d77b1435c90)
![20 adding curated csv delimited text](https://github.com/user-attachments/assets/dead2fdd-b248-458c-9510-eed4d6f6b132)
![21 three datasets](https://github.com/user-attachments/assets/3daf89f2-b481-4480-bead-e006c8d308b2)
![upload data set in data factory for the downloaded dataset uploaded to the storage account container](https://github.com/user-attachments/assets/cbcf7270-a24a-488b-b708-69b83b2e78d3)
![22 dataset upload to raw container](https://github.com/user-attachments/assets/1377ca2e-65ab-4c12-b1b3-c56430509ace)
![23 pipeline move copy transform](https://github.com/user-attachments/assets/11c6e6b0-96a9-46b2-9311-2b1f1ac9c04d)
![24 validate copy data](https://github.com/user-attachments/assets/af366c86-a436-462c-bafd-980c37388f1f)
![25 publish all](https://github.com/user-attachments/assets/937c0916-59cd-49ba-8fb7-2d4facd3d6fa)
![26 pipeline trigger now](https://github.com/user-attachments/assets/5b77aa20-e767-47c7-a33a-100777ce1ca0)
![27 monitor pipeline](https://github.com/user-attachments/assets/a14e674e-6eb1-46be-b5e6-1756a2fa6125)
![28 csv file has been copied over using the pipeline](https://github.com/user-attachments/assets/29074ae9-dc48-4369-ac9a-a07173ad4f74)
![29 dataflow](https://github.com/user-attachments/assets/f4ae6589-a1a5-407d-9031-daa45e0dcd3d)
![30 connect pipeline to dataflow on completion](https://github.com/user-attachments/assets/72aa141c-75a6-4577-a0b5-20a0f052536d)
![31 publish](https://github.com/user-attachments/assets/809eeb00-a550-41d0-bb71-cbe84241c0ef)
![32 results combined through dataflow connected with the pipeline and published after validating and debugging checking in monitor](https://github.com/user-attachments/assets/4455611e-9aa9-4132-8eb2-c12a0551bc87)
![33 publish complete](https://github.com/user-attachments/assets/9e82816c-addd-4ebc-a1f9-d140737c3523)






