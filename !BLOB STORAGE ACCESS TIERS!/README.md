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
