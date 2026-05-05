# T-Pot Honeypot Deployment on AWS EC2

## 📌 Overview
This project demonstrates the deployment of a T-Pot honeypot on an AWS EC2 Ubuntu instance. The system is designed to capture, monitor, and analyze real-world cyber attacks using multiple honeypot services and the Elastic Stack (Kibana).

---

## 🛠️ Technologies Used
- AWS EC2
- Ubuntu 24.04 LTS
- Docker & Docker Compose
- T-Pot Community Edition (T-Pot CE)
- Elastic Stack (Elasticsearch, Kibana)
- SSH (Secure Shell)

---

## ⚙️ Deployment Steps

### 1. Launch EC2 Instance
- Created an EC2 instance on AWS
- Selected Ubuntu 24.04
- Chose appropriate instance type
- Configured key pair for SSH access

---

### 2. Configure Security Groups
- Allowed inbound traffic:
  - SSH (Port 22)
  - HTTP (Port 80)
  - HTTPS (Port 443)
  - Custom TCP ports required by T-Pot
- Allowed outbound traffic for internet access

---

### 3. Assign Elastic IP
- Allocated and attached an Elastic IP address
- Ensured consistent access to the honeypot server

---

### 4. Connect via SSH
```bash
ssh -i honey.pem ubuntu@<your-public-ip>

### 5. Clone T-Pot Repository
```bash
git clone https://github.com/telekom-security/tpotce
cd tpotce
```

---

### 6. Install T-Pot
```bash
sudo ./install.sh
```
- Follow the installation prompts  
- Select the standard installation setup  
- Reboot the system after installation  

---

### 7. Verify Installation
```bash
systemctl status tpot
```

---

## ⚠️ Challenges Faced
- Encountered permission denied errors during setup  
- Faced GitHub cloning issues due to network connectivity  
- Initial SSH configuration problems  
- Received "400 Bad Request" errors when accessing the web interface  
- Misconfigured security groups initially blocked required ports  

---

## ✅ Conclusion
This project demonstrates the successful deployment of a cloud-based honeypot using T-Pot on AWS EC2. The system captures and visualizes real-world attack data through the Elastic Stack, providing insight into attacker behavior and potential vulnerabilities. It highlights the importance of proper network configuration, security group management, and system setup in cloud-based cybersecurity environments.
Deploy multiple honeypots across regions



