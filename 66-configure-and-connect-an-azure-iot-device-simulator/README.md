# Configure and Connect an Azure IoT Device Simulator
Simulate an IoT device to test telemetry and cloud connectivity no physical hardware required.

## Learning Objectives
- Create and register a simulated IoT device in Azure
- Modify telemetry code in a Raspberry Pi simulator
- Confirm message delivery to Azure IoT Hub
- View telemetry data in blob storage

## Register a Simulated Device
- In IoT Hub → Device Management > Click Devices
- Click + Add Device
- Device ID: myLabDevice 
- Leave defaults > Click Save
- Click the new device → Copy the Primary Connection String

## Launch Raspberry Pi Simulator
- Open the Azure IoT Raspberry Pi Simulator
- In the code pane, locate line 15 > Replace the connection string with your copied value
- Make sure it’s wrapped in single quotes
- Click Run > Observe telemetry messages and flashing light
- Click Stop to end the simulation

## Modify Telemetry Code
In the getMessage function:

Convert temperature to Fahrenheit:

```js
temperature: ((data.temperature_C) * 1.8) + 32,
```

Add barometer reading:

```js
barometer: data.pressure_hPa,
Click Run → Observe updated telemetry
```
Click Stop to end

## Confirm Message Delivery
- In Azure Portal > IoT Hub > Overview
- Check IoT Hub Usage tile > Confirm at least 1 message
- Click Device to cloud messages graph > Expand to view full day

## View Messages in Blob Storage
- Go to the linked Resource Group > Open the Storage Account
- Navigate to: Data Storage > Containers > telemetry
- Drill into folders > Locate .json blobs
- Right-click > Download to view message contents

### Completion
Successfully simulated an IoT device, sent telemetry to Azure, and verified message delivery in storage.

---

## Lab Outpupt Screenshots

![1](https://github.com/user-attachments/assets/d675961f-f89d-4356-b1c7-38689387e620)
![2](https://github.com/user-attachments/assets/c13dac04-6d86-4af2-9906-6beb97f438f0)
![3](https://github.com/user-attachments/assets/eae87a5e-5122-4a5e-8f79-fa82ee1ce4b2)
![4](https://github.com/user-attachments/assets/d8acca42-f700-413b-a62e-b2c607f9529d)
![5](https://github.com/user-attachments/assets/d5bd3266-9a41-4f58-a539-86160c9c9bdf)
![6](https://github.com/user-attachments/assets/c3bc4b99-1bfb-453c-af5b-cb6b44965548)
![7](https://github.com/user-attachments/assets/a135cd57-5aaa-4705-b33f-d6860ee301fc)
![8](https://github.com/user-attachments/assets/64ab2d7c-2efb-4f5b-b172-337f698e2e63)
![9](https://github.com/user-attachments/assets/5f27bf94-ff58-447e-bee3-7611e950155e)
![10](https://github.com/user-attachments/assets/8b3ed585-182b-4b0f-9899-abd223ff4c49)
![11](https://github.com/user-attachments/assets/5337450f-93a9-438e-90a1-766b2a48c3c2)
![12](https://github.com/user-attachments/assets/0724bfbd-12d0-4fba-9422-d5ccf16583ca)
![13](https://github.com/user-attachments/assets/382667cd-2968-4ed9-9072-02baf0c222ce)
![14](https://github.com/user-attachments/assets/86fdf917-f1d3-45e0-961a-af9c0ab77284)
![15](https://github.com/user-attachments/assets/74571999-a07c-4c87-ab18-a074c7ba89ff)
![16](https://github.com/user-attachments/assets/3e392063-52bd-407a-964d-f910e5c51177)
![17](https://github.com/user-attachments/assets/e7250d80-e4f8-4e10-a2a1-ba13895a804f)
![18](https://github.com/user-attachments/assets/383ca881-da49-4c87-a8f5-7c8425fa9dc6)
![19](https://github.com/user-attachments/assets/3263fb08-8ace-4f63-a4c8-30620ecf2243)
![20](https://github.com/user-attachments/assets/0b6a7ffb-2005-4fef-bcb7-5d570d62e7d5)
![21](https://github.com/user-attachments/assets/885dfec8-d79c-4c2b-aca3-98c79b215314)
![22](https://github.com/user-attachments/assets/5afbd6fb-2fd7-4ed5-aec1-1115475c529d)
![23](https://github.com/user-attachments/assets/e9403fd8-872a-495f-8a7f-77ee7e62550e)

