# Investigate a Security Incident in Azure

This lab guides you through investigating a suspected security incident using Microsoft Sentinel, analyzing authentication anomalies, and implementing automated response actions.

## Learning Objectives

### Investigate Anomalous Sign-In Activity
- Use Microsoft Sentinel to analyze incident data.
- Identify suspicious user behavior and compare activity patterns.
- Differentiate between legitimate and malicious access attempts.

### Validate the Security Incident
- Filter authentication events to assess login success/failure.
- Detect timing anomalies and behavioral clues.
- Confirm whether the incident is genuine or a false positive.

### Implement Automated Response
- Configure an automation rule to respond to similar threats.
- Use Logic Apps to create a playbook (e.g., Stop VM).
- Test alert logic and verify incident lifecycle handling.

## Step-by-Step Summary

### Access Sentinel Workspace
- Navigate to **Microsoft Sentinel** in Azure.
- Select the appropriate workspace tied to your lab.

### Review Incidents
- Go to **Incidents** under Threat Management.
- Select the incident and click **View full details**.
- Review alerts, entities, and timeline.

### Analyze Authentication Logs
- Use **Log Analytics** to query sign-in events.
- Apply filters for failed logins, unusual IPs, and time-based anomalies.

### Run Playbook (Stop VM)
- From the incident page, click **Run playbook**.
- Select your automation rule (e.g., Stop VM).
- Confirm the playbook executed successfully.

## Tips

- Use **KQL** to refine your log queries.
- If the playbook UI hangs, try running it directly from **Logic Apps**.
- Document your findings and response actions for lab completion.

Recommended: Open Hands-on Labs in an incognito window for best performance.

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/b6b8e1c6-796a-45b4-a5e7-56f389cb061e)
![2](https://github.com/user-attachments/assets/c6bb5843-9ba8-4e38-bc31-3e52a4894055)
![3](https://github.com/user-attachments/assets/f05c8275-056d-4628-8f49-1b6f92fef3c5)
![4](https://github.com/user-attachments/assets/5f8ac650-79cf-4c43-9fd0-5e56e263763c)
![5](https://github.com/user-attachments/assets/b3412df2-b80c-4da7-93a9-4395204aed71)
![6](https://github.com/user-attachments/assets/98d0fc6e-f87e-4802-b33e-6aeb75a93daf)
![7](https://github.com/user-attachments/assets/5cf3c233-3703-4180-920f-c17f5c02fd7c)
![8](https://github.com/user-attachments/assets/7e4fb548-810e-462b-b7bf-93042d7e4a3a)
![9](https://github.com/user-attachments/assets/b617f4ce-c17a-4c42-87f5-7e1df1c37741)
![10](https://github.com/user-attachments/assets/a1777320-82dc-4f2c-9d5a-d54192ceaa73)
![11](https://github.com/user-attachments/assets/18ac9a85-a036-4bfe-bce4-84ecbbd86c20)
![12](https://github.com/user-attachments/assets/42f91fa9-e1fe-4b56-9380-7a948b33cab0)
![13](https://github.com/user-attachments/assets/ba35e144-b98b-49d9-b27c-cab054f3266c)
![14](https://github.com/user-attachments/assets/3a4522f0-130f-4665-bef2-4aa16597409a)
![15](https://github.com/user-attachments/assets/3c841f3a-8c73-4a03-8e1a-0830be7919f4)
![16](https://github.com/user-attachments/assets/98323221-7485-40df-aeb8-0f6940583810)
![17](https://github.com/user-attachments/assets/9bf562e2-c27d-47ed-a7d7-cf4c0fff3018)
![18](https://github.com/user-attachments/assets/035f6539-689e-406d-93c5-3ca1586f202a)
![19](https://github.com/user-attachments/assets/3f7c99e9-b991-43fc-89ce-bbc22e0a6db9)
![20](https://github.com/user-attachments/assets/a1fcda97-1ee2-4e0a-a589-d86165542a4e)
![21](https://github.com/user-attachments/assets/4bd15658-ee3a-472f-aae6-5ea8254eacd4)
![22](https://github.com/user-attachments/assets/4be511a7-2349-4904-8408-c74f42dcea96)
![23](https://github.com/user-attachments/assets/a5dba48d-883c-427f-8e15-4d7e33643f70)
![24](https://github.com/user-attachments/assets/f546f291-3750-4a30-9806-c330d4495f7c)
![25](https://github.com/user-attachments/assets/00cf1ae9-ac96-4f1a-9982-9d8a92022924)
![26](https://github.com/user-attachments/assets/b8fcc52a-3c8e-4cdc-aa57-4fedaab1156b)

