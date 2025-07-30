# Configuring and Customizing the Azure Cloud Shell

## Objectives

- Log in to the Azure portal and launch Azure Cloud Shell
- Choose Bash or PowerShell interface
- Customize shell settings including font size and font face
- Launch multi-session terminal with alternate shell
- Create and download test files from alternate Cloud Shell

---

## Steps Performed

### Launch Cloud Shell

- Click the **>_ Cloud Shell icon** in the Azure Portal toolbar
- Choose **PowerShell** or **Bash** terminal based on preference
- Configure storage using advanced settings:
  - Select lab subscription and existing resource group
  - Use **Central US** for location
  - Create unique **Storage Account** and **File Share**

### Customize Terminal

- Customize **font size** and **font face** under Cloud Shell settings
- Adjust shell display preferences for accessibility and readability

### Switch Terminal Session

- Launch a new Cloud Shell session using the alternate terminal (e.g., if you started in PowerShell, switch to Bash)

### Create and Download Files

**Using Bash**:
```bash
  touch learncloud.txt
```

*Using PowerShell*:
```bash
touch learncloud2.txt
```

### Observations

- Cloud Shell interface was customizable and easy to configure
- Multi-terminal setup allowed seamless toggling between Bash and PowerShell
- File creation and download steps worked across both interfaces

---

## Lab Output Screenshots

![1 create a mount a new storage account to powershell cli](https://github.com/user-attachments/assets/a1a59728-3455-480b-88d0-53e9ea7991b8)
![2 change font size](https://github.com/user-attachments/assets/fe53d76a-972a-4737-8c47-6b27e70ab4df)
![3 change font in cli](https://github.com/user-attachments/assets/b2e301b4-f5eb-4a2f-949b-cc7dab747612)
![4 duplicate azure tab switch to bas touch learncloud txt ls switch to powershell tab ls check write and check bash for file](https://github.com/user-attachments/assets/ddce9c3e-d305-4635-960c-1b2d0d23e498)
![5 powershell touch learncloud01 ls in bash cli to view](https://github.com/user-attachments/assets/d16b222f-cb41-494c-a6d2-f0a1b524c3cc)
![6 download the created file from the other cli](https://github.com/user-attachments/assets/815c4f85-7405-465d-87ee-26bedeccc494)







