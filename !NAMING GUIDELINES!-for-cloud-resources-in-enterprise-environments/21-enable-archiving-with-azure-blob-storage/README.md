# Enable Archiving with Azure Blob Storage

This lab demonstrates how to change the **access tier** of blobs in a container to **Archive** using Azure Portal.

---

## Concepts Covered

- **Blob Access Tiers**: Hot, Cool, Archive
- Differences between Access Tier vs Access Level
- Implications of Archive tier (lower cost, slower retrieval)

---

## Steps to Archive a Blob

1. **Go to Azure Portal**
   - Navigate to your **Storage Account**.
   - Select **Containers**, then choose your target container.

2. **Select Blob to Archive**
   - Click on the blob you want to archive.
   - From the toolbar, choose **Change Tier**.

3. **Change Access Tier**
   - Select `Archive`.
   - Confirm your selection.

---

## Important Notes

- Blobs in `Archive` tier are **not immediately retrievable**.
- To read them, you must **rehydrate** them back to Hot or Cool tier first.
- Archived blobs still incur **storage charges**, but at the lowest tier.

---

## Verification

You can confirm the blob’s access tier:
- Open blob properties → Look under **Access Tier**
- Or use **Azure CLI**:
  ```bash
  az storage blob show \
    --account-name <your-storage-account> \
    --container-name <your-container> \
    --name <your-blob> \
    --query "properties.accessTier"
  ```

# Azure Blob Storage Access Tiers Explained

Understanding blob access tiers helps optimize both **cost** and **performance** when storing data in Azure.

---

## Access Tier Comparison Chart

| Tier        | Access Frequency         |   Storage Cost |   Speed to Access |   Min Retention Period | Best For                                 |
|-------------|--------------------------|------------------|---------------------|--------------------------|---------------------|
| **Hot**     | Frequently accessed       | High              | Immediate            | None                     | Active data, real-time applications        |
| **Cool**    | Infrequent (≥30 days)     | Medium            | Immediate            | 30 days                  | Backups, rarely accessed logs             |
| **Cold**    | Rare (≥90 days)           | Low               | Immediate            | 90 days                  | Compliance data, long-term archives       |
| **Archive** | Very rare (≥180 days)     | Lowest            | Delayed (rehydration) | 180 days                | Legal docs, historical data               |


## Key Points

- Choose a tier based on how often your app or users will access the data.
- Archive is cheapest but takes time to rehydrate (can be hours).
- Cold and Cool are fast but cheaper than Hot — ideal for aging data.
- Retention matters: Deleting blobs earlier than allowed incurs a fee.

---

## Tier Management Tips

- Use the **Azure Portal** or **CLI** to manually set tiers.
- Automate transitions with **Lifecycle Management Policies**.

```json
{
  "rule": {
    "name": "AutoMoveToArchive",
    "action": "Move to Archive",
    "condition": {
      "daysAfterLastModifiedGreaterThan": 180
    }
  }
}
```

---

## CLI to Check Blob Tier

```bash
az storage blob show \
  --account-name <your-storage-account> \
  --container-name <your-container> \
  --name <your-blob> \
  --query "properties.accessTier"
```

---

### Next Steps

- Set up **Lifecycle Management Policy** to auto-archive blobs after X days.
- Experiment with `Cool` vs `Archive` in performance and cost.

---

## Lab Output Screenshots

![1 storage account create container upload 3 blobs](https://github.com/user-attachments/assets/a53f7103-eb46-4ead-9ef8-0ad7301710f1)
![2 blob uploads access tiers hot alter](https://github.com/user-attachments/assets/ada0f774-5a3f-4349-a1df-fbaa099c5856)
![3 altered storage container blobs access tiers to hot cool and archive](https://github.com/user-attachments/assets/eb88ce1d-8ad8-4aef-9924-90e6a78d3f71)
![4 download hot and cool blobs unable to download archive would need to rehydrate priority takes a long time](https://github.com/user-attachments/assets/71a3c90d-770e-45f5-b114-cd67984b11da)




