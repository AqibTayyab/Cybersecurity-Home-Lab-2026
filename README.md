# Cybersecurity Home Lab Portfolio 2026

Welcome to my hands-on cybersecurity portfolio. This repository documents my journey through a 4-project intensive lab designed to build real-world SOC (Security Operations Center) skills.

**Inspired by:** The Social Dork (Royon)

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
To implement a defense-in-depth strategy by deploying an AI-powered WAF to protect a vulnerable web application from common OWASP Top 10 threats.

### **Lab Architecture**
* **Attacker:** Kali Linux
* **Defender:** Ubuntu 25.10 (hosting SafeLine WAF)
* **Target:** DVWA (Damn Vulnerable Web Application) running in a Docker container

### **Step-by-Step Execution**
1.  **Environment Setup:** Configured a virtual network in VirtualBox using a **Bridged Adapter** to allow seamless communication between Kali and Ubuntu.
2.  **WAF Installation:** Deployed Chaitin SafeLine WAF via Docker on the Ubuntu machine.
3.  **Victim App Deployment:** Launched the DVWA container on port 80.
4.  **Reverse Proxy Configuration:** Configured SafeLine to listen on port **8080** and forward clean traffic to the DVWA container.
5.  **Attack Simulation:** Used `curl` from my Kali machine to execute a SQL Injection payload: `id=1' OR '1'='1`.

### **Key Outcomes**
* **Interception:** The WAF successfully detected the malicious SQL syntax using its intelligent detection engine.
* **Blocking:** SafeLine returned a **403 Forbidden** status and a custom block page, preventing the attack from reaching the database.
* **Visibility:** Confirmed the attack signature and Attacker IP in the SafeLine management dashboard.

---

## Project 2: Wazuh SIEM Implementation (In Progress...)
*Currently deploying the Wazuh Indexer and Server to establish centralized security monitoring.*

---

### Contact & Networking
**Open to SOC Analyst and Cybersecurity internships. Let's connect!**
* **LinkedIn:** [Muhammad Aqib Tayyab](https://www.linkedin.com/in/muhammad-aqib-tayyab-ethical-hacker/)
* **YouTube:** [MuhammadAqibTayyab](https://www.youtube.com/@MuhammadAqibTayyab)
