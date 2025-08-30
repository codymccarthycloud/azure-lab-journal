# Restricting Access to Azure Virtual Network Resources

## Learning Objectives

## **Connect to Ubuntu Linux Virtual Machine**
   - Access the Azure Portal using lab credentials:
     - **Username**: `cloud_user_p_f2f65d95@realhandsonlabs.com`
     - **Password**: `ee6-4s5b`
   - Use **Azure Bastion** for secure SSH access:
     - Navigate to `lab-vm` in the portal.
     - Select **Connect > Bastion**.
     - Enter VM credentials:
       - **Username**: `cloud_user`
       - **Password**: `&8QLkV46wKbfLAb6LeFl`
     - Click **Connect** to launch the in-browser terminal.

## **Configure the Web Server**
   - Install Nginx via APT:
     ```bash
     sudo apt update
     sudo apt install nginx -y
     ```
   - Remove default start page:
(Lab)    
     ```bash
     sudo rm -f *
     ```
(Enterprise approach)
     ```bash
     sudo rm /var/www/html/index.nginx-debian.html
     ```
   - Download web app from GitHub directly to the Nginx root:
     ```bash
     cd /var/www/html
     sudo git clone https://github.com/your-repo/webapp/archive/main.zip
     ```

## **Allow Inbound Internet Traffic**
   - In the VM's **Networking** pane, add an inbound port rule:
     - **Port**: `80`
     - **Protocol**: `TCP`
     - **Action**: `Allow`
     - **Description**: `HTTP`
   - Verify web server by navigating to the public IP:
     - [Midnight Movers Web App](http://4.157.247.143/)

---

### Conclusion

- Successfully restricted access using NSG rules.
- Verified Nginx deployment and public accessibility.
- Used Azure Bastion to avoid exposing public SSH ports.
*Tip*: Always use Bastion for secure VM access in production environments—no public IP exposure, no local SSH client required.

---

## Lab Output Screenshots

![1](https://github.com/user-attachments/assets/2810d4e2-3a29-4adb-baff-21164715beaa)
![2](https://github.com/user-attachments/assets/13cace56-54ac-4343-97cc-1da19da19a4f)
![3](https://github.com/user-attachments/assets/bac9c125-717e-4f6a-a85f-5b3793afe9d6)
![4](https://github.com/user-attachments/assets/9680bc7e-68e9-4f40-8904-37c732c48312)
![5](https://github.com/user-attachments/assets/ab5b97e3-2c57-4112-8217-232dc5d3ac1f)
![6](https://github.com/user-attachments/assets/cc98c982-af8b-438e-ad96-5178bf20f719)
![7](https://github.com/user-attachments/assets/a86148cc-1dbe-4414-a6dc-998a38ce79d0)
![8](https://github.com/user-attachments/assets/0efb5ef6-be60-4907-ab67-902f4986bd3c)
![9](https://github.com/user-attachments/assets/9e2343c0-95f1-4b16-a388-a59396b72aaa)
![10](https://github.com/user-attachments/assets/00547980-1ec5-4eac-a095-0a7358ac207c)
![11](https://github.com/user-attachments/assets/0531b3c2-9ee5-44ef-8eeb-611d6a476352)
![12](https://github.com/user-attachments/assets/4044461a-98ee-45ab-be5d-e49faa2599d6)
![13](https://github.com/user-attachments/assets/ec5f303c-962c-4cc6-bd4e-e3d846af0f8c)
![14](https://github.com/user-attachments/assets/35fce7f6-2b72-46f2-9a61-0d1bb9c67cbd)

