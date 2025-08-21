# Create a Scheduled Function with Azure Functions CLI

## Initialize the Function App
```bash
mkdir functest
cd functest
func init MyFunctionApp 
2 (dotnetIsolated)
1 (C#) 
```

## Create a Timer Trigger Function
```bash
func new 
4 (TimerTrigger)
```
This generates a function that runs on a schedule defined by a CRON expression.

## Customize the Timer Schedule
Open ScheduledFunction.cs and update the CRON expression 5 minutes to 1:

```csharp
[Function("ScheduledFunction")]
public void Run([TimerTrigger("0 */5 * * * *")] TimerInfo timerInfo)
{
    _logger.LogInformation($"Timer triggered at: {DateTime.UtcNow}");
}
```
This example runs every 5 minutes. You can adjust the CRON string as needed.

## Set variables and show connection string

```bash
ACC_NAME=$(az storage account list [0].name -o tsv
az storage account show-connection-string -n $ACC_NAME --query "connectionString" -o tsv
```
Copy connection string and paste it into local.settings.json "AzureWebJobsStorage": "<your-storage-connection-string>"

## Configure local.settings.json
```json
{
  "IsEncrypted": false,
  "Values": {
    "AzureWebJobsStorage": "<your-storage-connection-string>",
    "FUNCTIONS_WORKER_RUNTIME": "dotnet"
    "FUNCTIONS_INPROC_NET8_ENABLED": "1"
  }
}
```

## Check Your .csproj
Make sure you're targeting .NET 8 and using the correct SDK version:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net8.0</TargetFramework>
    <AzureFunctionsVersion>v4</AzureFunctionsVersion>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Microsoft.NET.Sdk.Functions" Version="4.5.0" />
  </ItemGroup>
</Project>
```

## Run the Function 
```bash
func host start
```
You should see logs indicating the timer function is executing on schedule.

### CRON Expression Reference
Expression	Description
"0 */5 * * * *"	Every 5 minutes
"0 0 * * * *"	Every hour
"0 0 9 * * *"	Every day at 9 AM
"0 0 9 * * 1"	Every Monday at 9 AM

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/076dc99e-bba5-48c1-8363-49b9807cca2c)
![2](https://github.com/user-attachments/assets/7c1f6110-38ed-4ed9-a7c9-f9e55e8dc2b8)
![3](https://github.com/user-attachments/assets/b1aa7d63-25a7-477f-b38c-016b230bf58c)
![4](https://github.com/user-attachments/assets/3ba293ce-eea3-49ff-9ced-4391cfbda42f)
![5](https://github.com/user-attachments/assets/f7be1bbc-417c-4ff8-abfb-b408aa4064a5)
![6](https://github.com/user-attachments/assets/6aa4d5e4-985b-41bb-8b45-76664c219534)
![7](https://github.com/user-attachments/assets/735eddd0-350d-42b5-9ee2-302acee40d4d)
![8](https://github.com/user-attachments/assets/8330190b-e045-4a32-a286-dd205486cc49)
![9](https://github.com/user-attachments/assets/76badb09-3d02-43b5-8d3c-5e3407eb6bdf)
![12](https://github.com/user-attachments/assets/5a0328b0-389b-454b-af4d-c8ba8065f682)
![13](https://github.com/user-attachments/assets/02606330-72d0-4200-87ba-c86ceb789137)
