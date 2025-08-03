# Create a Scheduled Function with the Azure Functions CLI


## 1. Initialize a New Function App

```bash
mkdir functest
cd functest
func init  
```

## 2. Add a Timer-Triggered Function
```bash
func new 
```
Select dotnet-isolated and C#

## 3. Update the Schedule Expression
Open TimerFunction.cs and locate the TimerTrigger attribute:

```bash
code .
```

```csharp
[Function("TimerFunction")]
public static void Run(
    [TimerTrigger("0 */5 * * * *")] TimerInfo myTimer,
    FunctionContext context)
{
    var logger = context.GetLogger("TimerFunction");
    logger.LogInformation($"Function ran at: {DateTime.Now}");
}
Change the expression to run every minute:

csharp
[TimerTrigger("0 */1 * * * *")]
Save your changes.
```

## 4. Configure Local Settings
In local.settings.json, set your storage connection string:

```json
{
  "IsEncrypted": false,
  "Values": {
    "AzureWebJobsStorage": "<Your_Storage_Connection_String>",
    "FUNCTIONS_WORKER_RUNTIME": "dotnet-isolated"
  }
}
```
The storage connection is required for timer triggers to fire locally.

## 5. Edit functest.csproj
```bash
dotnet --version
```
Edit functest.csproj change dotnet V8 to V9:
- net9.0

## 5. Run the Function Locally
```bash
func host start
```
Watch the console logs; you should see your function executing once per minute.

## Lab Output Screenshots

![1 mkdir functest cd functest func init func new](https://github.com/user-attachments/assets/11be4cea-71db-4f49-93bb-00c4bc9a74ab)
![2 acc name az storage show connection string](https://github.com/user-attachments/assets/5668dd61-10bb-4fba-87e2-90ef8fb09d06)
![3 code](https://github.com/user-attachments/assets/bac3a087-16b9-43fa-b0db-b23526fa9028)
![4](https://github.com/user-attachments/assets/35905f77-afef-4f6f-b33d-3453d430840e)
![5 local settings json connection string](https://github.com/user-attachments/assets/b225b0fa-da6e-4b1a-8e7a-76e5a7dc5361)
![6](https://github.com/user-attachments/assets/43a58884-f8ba-41ec-8ba1-5acbb2d6f4a0)
![7](https://github.com/user-attachments/assets/95f5326a-7c5d-4121-b063-c44103da68f4)
![8](https://github.com/user-attachments/assets/7ef95a83-84f0-4244-ac6b-a772db5cb65e)
![9](https://github.com/user-attachments/assets/0751410b-b801-4bc1-bf18-d600aa3e542a)
![10](https://github.com/user-attachments/assets/aafa2318-bc7f-4d94-aac5-e1c6fd812b58)
![11](https://github.com/user-attachments/assets/9f5c7f65-3085-4399-b599-e9ba616afede)
