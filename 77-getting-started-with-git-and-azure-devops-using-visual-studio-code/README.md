# Getting Started with Git and Azure DevOps Using Visual Studio Code

## Overview

- Log into Azure VM
- Create a Git repository in Azure DevOps
- Clone the repo using Visual Studio Code in an Azure VM
- Making and committing changes
- Syncing updates back to Azure DevOps

---

## Create Azure DevOps Project & Repo
- Open an **Incognito browser window**
- Go to [Azure DevOps Portal](https://dev.azure.com)
- Sign in using lab credentials
- Create a new project:
  - Name: `Lab Project`
  - Visibility: Private
- Navigate to **Repos > New Repository**
  - Name: `IT Ops Repo`
  - Check “Add a README”
  - Click **Create**

## Launch Visual Studio Code
- Open VS Code from the Start menu
- Open a new terminal:
  ```bash
  git config --global user.name "Your Name"
  git config --global user.email "your.email@example.com"
  ```

## Clone the Repository
- In Azure DevOps, click Clone > HTTPS > Copy URL
  In VS Code:
- Open File
- Clone Git
- Choose a local folder to store the repo
- Authenticate using lab credentials
- Click Open Repository 

## Edit and Commit Changes
- Open README.md in VS Code
  Add a line like:
- IT Ops Repo for Scripts and Files

## Create and Commit Script File
- Save the file (Ctrl + S)
- Import into the Repo Documents Folder
- Inspect in Visual Studio
- Add a commit message: "Initial setup and sync"
- Commit
- Sync in the bottom setting options to push changes

## Verify in Azure DevOps
- Refresh the repo page
- Confirm the updated README.md and Script.txt is visible
- Click the file > History to view your commit

### Key Takeaways
- Azure DevOps provides a fully managed Git experience
- VS Code integrates Git operations seamlessly
- Authentication and repo sync are intuitive once configured
- Always use Incognito mode to avoid credential conflicts

### Completion Checklist
- Created Azure DevOps project and repo
- Cloned repo using VS Code
- Made and committed changes
- Synced updates and verified in Azure DevOps

### Tip: Use the Command Palette (Ctrl + Shift + P) for quick access to Git commands in VS Code.

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/e37126cd-ce2d-43ef-953d-2f09f4b81dd1)
![2](https://github.com/user-attachments/assets/441853bf-7c10-42ab-aa90-8a326bc8ec81)
![3](https://github.com/user-attachments/assets/41d881ad-176d-44f2-b518-821009cad571)
![4](https://github.com/user-attachments/assets/8ceb4328-402a-461f-b6db-bdfa4b91f787)
![5](https://github.com/user-attachments/assets/e18c7d52-595c-4ec8-b681-2b1852c12db1)
![6](https://github.com/user-attachments/assets/07e45f8e-58e5-4b3d-9708-7e351a352ad6)
![7](https://github.com/user-attachments/assets/122bacdc-1414-4862-a07f-9450aad9110e)
![8](https://github.com/user-attachments/assets/331a528c-073e-4d1d-aedc-4d9665387618)
![9](https://github.com/user-attachments/assets/12798ff2-a12f-400e-93b3-077234d4f41e)
![10](https://github.com/user-attachments/assets/38efa04e-100c-4005-8a31-2e09049c355a)
![11](https://github.com/user-attachments/assets/22e702ff-f3a8-4bcd-8a60-16ec93f4a48a)
![12](https://github.com/user-attachments/assets/1c1cc07c-abf7-4e2c-8998-82b3bbc0a25a)
![13](https://github.com/user-attachments/assets/cc3707da-4a87-40e9-8fbf-06ecaf1d8ad5)
![14](https://github.com/user-attachments/assets/d29d3e77-a89f-404c-8e3b-e77ae736896b)
![15](https://github.com/user-attachments/assets/74210590-ebcf-491c-94e2-1f9f468258bc)
![16](https://github.com/user-attachments/assets/e0767c12-8b9b-4e89-a81e-fd334da7a193)
![17](https://github.com/user-attachments/assets/f519988e-9a66-4c77-9e4c-52601ec281b2)
![18](https://github.com/user-attachments/assets/925fe46a-1b27-43ca-ae8e-8d2746861fcb)
![19](https://github.com/user-attachments/assets/1d938fa1-8ad7-4b7b-8086-cf038be28b07)
![20](https://github.com/user-attachments/assets/bce444a8-a54a-4b8f-8c33-8d9b764468eb)
![21](https://github.com/user-attachments/assets/711ae265-0050-4d96-952f-33f5fc52df27)
![23](https://github.com/user-attachments/assets/47949e71-2d6a-46cb-b99c-1519b535a737)
![24](https://github.com/user-attachments/assets/b1b8ba17-7306-420f-aaef-3a14d18b6caa)
![25](https://github.com/user-attachments/assets/88d2a6dc-3b6f-4663-bde4-3ba91bf08a9e)
![26](https://github.com/user-attachments/assets/3201ab42-980f-4796-8db0-706d6a717e2d)
![22](https://github.com/user-attachments/assets/14759e37-1cdd-4b7b-a580-a4e5f64a0ce1)
![27](https://github.com/user-attachments/assets/6ca084ac-bf0d-4868-8704-cdbec1e93821)
![28](https://github.com/user-attachments/assets/f9555494-5781-473d-8d6f-1374b5a2118e)
![29](https://github.com/user-attachments/assets/0f52ee91-6b13-488f-bd6e-85163509d427)
![30](https://github.com/user-attachments/assets/3367a8b0-ba4b-445f-910e-309902155aff)
![31](https://github.com/user-attachments/assets/80d11360-341f-49e1-9cb0-2a216bd5d174)
