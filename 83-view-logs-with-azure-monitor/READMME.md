# View Logs with Azure Monitor

Trigger a Durable Functions orchestration and view logs using Azure Monitor and Application Insights.


## Trigger a New Durable Functions Orchestration

- Log into the Azure Portal.
- Navigate to the **NewOrderOrchestration_HttpStart** function.
- Click **Get Function URL**.
- Ensure **default (function key)** is selected.
- Copy the URL and paste it into a new browser tab to trigger the function.


## View Log Output in Azure Monitor

- In the Azure Portal, go to the **Invocations** tab for `NewOrderOrchestration_HttpStart`.
- Refresh until an invocation appears.
- Click the **date-time link** to open the invocation details.
- Logs will appear in a popout window.
- Repeat for other functions:
   - `NewOrderOrchestration`
   - `CreateTicket`
   - `CreateNightlyReport`


## View Logs in Application Insights

- In the log view, click **Run Query in Application Insights**.
- This opens Application Insights with a pre-populated KQL query.
- Optionally, experiment with:
   - KQL syntax
   - Application Insights UI features


## Learning Objectives

- Trigger a Durable Functions orchestration
- View logs via Azure Monitor
- Analyze logs using Application Insights

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/b36164fe-e2ad-4825-99dc-c961456a2444)
![2](https://github.com/user-attachments/assets/519e6252-ec26-4512-86d3-7b071ca62662)
![3](https://github.com/user-attachments/assets/5d73427f-a998-49bf-a1b3-b9b64409a7c9)
![4](https://github.com/user-attachments/assets/b75c968e-0862-44c7-a3c1-8f0136136b13)
![5](https://github.com/user-attachments/assets/ae99e3ff-bf4c-414b-a957-34e215717af7)
![6](https://github.com/user-attachments/assets/e804c6df-a406-4124-9201-ac7f5c56b2c7)
![7](https://github.com/user-attachments/assets/34f09187-cd34-4b64-a7a7-ef6f1e23bca1)
![8](https://github.com/user-attachments/assets/099a5a22-9a33-4233-a7ef-c782740334ff)
![9](https://github.com/user-attachments/assets/80e1d650-fc51-44c0-8b83-27cda4ed3f04)
![10](https://github.com/user-attachments/assets/834b8d25-1896-4b1f-866b-14a65ad097b7)
![11](https://github.com/user-attachments/assets/9457b252-54f3-4862-ae5b-2bff84884d21)
![12](https://github.com/user-attachments/assets/abffb6bb-969d-4fc5-b961-57569108fd8b)
![13](https://github.com/user-attachments/assets/c67a7fed-d1cc-43ab-abfd-8714504e1fe2)
![14](https://github.com/user-attachments/assets/2384bc03-e29c-42bf-9216-1c1ed2711c76)
![15](https://github.com/user-attachments/assets/a188bc68-5434-415a-96cf-267793b870a1)
![16](https://github.com/user-attachments/assets/131960bc-0868-4cc0-8641-325be041a150)
![17](https://github.com/user-attachments/assets/56966249-e3a6-475b-8ec2-dd6cc2741f05)

> 💡 Tip: For best results, open Hands-on Labs in an incognito window.

