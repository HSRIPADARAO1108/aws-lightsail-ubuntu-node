# AWS Lightsail: Manual Node.js Deployment on Ubuntu

This project demonstrates a manual **Infrastructure as a Service (IaaS)** deployment. While my other projects use automated "Serverless" tools, this repository proves my ability to manage the **Operating System (OS)**, security, and process persistence manually on a Linux VPS.

## 🚀 Live Deployment
**Static IP Address:** `http://3.108.194.63:8080`

---

## 🛠️ Infrastructure Implementation

### 1. Server & OS Management
Launched an **Ubuntu 22.04 LTS** instance via Amazon Lightsail. Unlike managed services, I have full root access to this OS to install and configure software as needed.
![Lightsail Instance](./images/lightsail-instance.png)

### 2. Manual Network Security
Configured the **IPv4 Firewall** to allow inbound traffic on **Port 8080**. This step is required to make the Node.js application accessible to the public internet.
![Firewall Config](./images/firewall-config.png)

### 3. Production Process Persistence
Utilized **PM2** to manage the application process. This ensures the app stays "online" even if the SSH session is closed or the server reboots.
![PM2 Status](./images/pm2-status.png)

### 4. Site Verification
The application is successfully served via the Static IP, proving the server and firewall are correctly configured.
![Live Site](./images/live-site.png)

---

## ❓ FAQ: Understanding the Architecture

During this project, I explored the critical differences between **App Runner (Service)** and **Lightsail (Server)**. Here is the summary:

**Q: What is the main difference between App Runner and Lightsail?**
**A:** Think of App Runner as a **Hotel** (AWS manages everything) and Lightsail as an **Apartment** (You bring the furniture/software). In App Runner, you only handle the **Code**. In Lightsail, you handle the **OS and the Server**.

**Q: Why use GitHub if I am managing the server manually?**
**A:** GitHub acts as the secure bridge. I push code from my local machine to GitHub, and then "pull" it into the Ubuntu OS. This ensures code integrity and provides a backup.

**Q: What does "handling the OS" actually mean?**
**A:** In App Runner, you just upload code and do nothing else. In Lightsail, you must log into the Ubuntu terminal and manually install Node.js, Git, and PM2. You are the **System Administrator**.

---
**Architected by [HSRIPADARAO1108](https://github.com/HSRIPADARAO1108)**
