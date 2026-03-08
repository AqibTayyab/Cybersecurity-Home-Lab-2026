# Cybersecurity Home Lab Portfolio 2026

Welcome to my hands-on cybersecurity portfolio. This repository documents my journey through a 4-project intensive lab designed to build real-world SOC (Security Operations Center) skills.

**Created by:** [Muhammad Aqib Tayyab](https://www.linkedin.com/in/muhammad-aqib-tayyab-ethical-hacker/)

**Inspired by:** [The Social Dork (Royden Rahul Rebello)](https://www.youtube.com/@thesocialdork1133)

---

### Technology Stack & Tools
![Ubuntu](https://img.shields.io/badge/Ubuntu-E94331?style=for-the-badge&logo=ubuntu&logoColor=white)
![Kali Linux](https://img.shields.io/badge/Kali_Linux-557EBF?style=for-the-badge&logo=kali-linux&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![VirtualBox](https://img.shields.io/badge/VirtualBox-183A61?style=for-the-badge&logo=virtualbox&logoColor=white)
![Wazuh](https://img.shields.io/badge/Wazuh-00A9E0?style=for-the-badge&logo=wazuh&logoColor=white)

### Skills Learned
* **Infrastructure:** Virtual Networking (Bridged/NAT), Linux Administration (Ubuntu/Kali).
* **Defensive Security:** WAF Configuration, Reverse Proxy Setup, Load Balancing.
* **Offensive Security:** SQL Injection (SQLi) Testing, Payload Crafting.
* **Security Operations:** SIEM Deployment (Wazuh), Log Analysis, Real-time Threat Detection.
* **DevOps:** Containerization with Docker and Docker-Compose.

---

## Project 1: SafeLine Web Application Firewall (WAF) Deployment

### **Objective**
To implement a defense-in-depth strategy by deploying an AI-powered WAF as a reverse proxy to protect a vulnerable web application from common OWASP Top 10 threats.

### **Lab Architecture**
* **Attacker:** Kali Linux (Offensive testing).
* **Defender:** Ubuntu 25.10 (Hosting SafeLine WAF).
* **Target:** DVWA (Damn Vulnerable Web Application) running in a Docker container.

### **Step-by-Step Technical Execution**
1.  **Network Plumbing:** Configured a virtual network in VirtualBox using a **Bridged Adapter**. This allowed the VMs to communicate as independent nodes on the physical local network.
2.  **System Hardening:** Resolved Ubuntu 25.10 driver issues by switching to standard GNU tools to properly install **VirtualBox Guest Additions**.
3.  **WAF Deployment:** Installed Chaitin SafeLine WAF via Docker. Configured the management console to act as a **Reverse Proxy**, listening on port **8080** and forwarding "clean" traffic to the application on port **80**.
4.  **Victim App Launch:** Deployed the DVWA container: `sudo docker run --rm -it -p 80:80 vulnerables/web-dvwa`.
5.  **Attack Simulation:** Executed a SQL Injection attack from Kali using `curl`: 
    `curl "http://<Ubuntu-IP>:8080/?id=1'%20OR%20'1'='1"`.

### **Key Outcomes**
* **Real-time Interception:** The WAF's intelligent engine detected the malicious SQL syntax and returned a **403 Forbidden** status.
* **Prevention:** The attack was stopped at the perimeter; the vulnerable database was never reached.
* **Forensic Visibility:** Logged and analyzed the attack signature, timestamp, and Attacker IP in the SafeLine Dashboard.

---

## Project 2: Wazuh SIEM Implementation (In Progress...)
*Currently deploying the Wazuh Indexer, Server, and Dashboard to establish centralized security monitoring and File Integrity Monitoring (FIM).*

---

### 📞 Contact & Networking
**Open to SOC Analyst and Cybersecurity internships. Let's connect!**
* **LinkedIn:** [Muhammad Aqib Tayyab](https://www.linkedin.com/in/muhammad-aqib-tayyab-ethical-hacker/)
* **YouTube:** [MuhammadAqibTayyab](https://www.youtube.com/@MuhammadAqibTayyab)
