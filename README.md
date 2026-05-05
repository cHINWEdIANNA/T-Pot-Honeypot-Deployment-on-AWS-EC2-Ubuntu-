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

5. Clone T-Pot Repository
git clone https://github.com/telekom-security/tpotce
cd tpotce

6. Install T-Pot
sudo ./install.sh
Followed installation prompts
Selected standard installation setup
Rebooted system after installation

7. Verify Installation
Check T-Pot service:
systemctl status tpot

⚠️ Challenges Faced
Permission denied errors during setup
GitHub cloning issues due to network connectivity
SSH configuration challenges
Port access errors (400 Bad Request)
Security group misconfiguration initially blocking access

✅ Conclusion

This project successfully demonstrates how a cloud-based honeypot can be deployed to monitor and analyze real-world cyber threats. Using T-Pot and the Elastic Stack, it is possible to gain valuable insights into attacker behavior and network vulnerabilities.


🚀 Future Improvements
Automate deployment using scripts
Add alerting system for real-time attack notifications
Integrate threat intelligence feeds
Deploy multiple honeypots across regions



