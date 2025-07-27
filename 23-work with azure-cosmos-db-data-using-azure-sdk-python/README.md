# Azure Cosmos DB Lab – Python SDK CLI Workflow

```bash
# Clone the lab repo, navigate to the Python folder, install the SDK
git clone https://github.com/pluralsight-cloud/content-az-204-developing-solutions-for-microsoft-azure.git AZ204_Labs 
cd AZ204_Labs/work_with_cosmos/python/
pip install --user azure-cosmos
```

# Upload your Python test script (cosmostest.py) via the Cloud Shell upload button (lands in /home/cloud)
# Move it into the lab folder
mv ~/cosmostest.py ./

# Edit cosmostest.py to set your Cosmos DB connection string (from Portal → Keys), database/container names, and JSON payload
# Run the script to create the DB, container, and insert the JSON item
python cosmostest.py

---

## Lab Output Screenshots

![1 git clone url AZ204_labs extension cd to folder AZ204_Labs work_with_cosmos python pip install --user azure-cosmos](https://github.com/user-attachments/assets/decffbcb-6b59-433a-92de-bb446a9096bc)
![3 python script my connection string](https://github.com/user-attachments/assets/3209bbfe-f580-4377-84e5-74569c6c2a83)
![2 run py file for cosmos db container and json file creation](https://github.com/user-attachments/assets/1866af1e-df2c-491d-a3ec-3c4e91880f64)

