# **🛡️ Comprehensive Penetration Testing Using Network, Web Application, and Social Engineering Techniques**

This project demonstrates a full penetration testing workflow across **three major attack surfaces**:
1️⃣ **Network Penetration Testing (Metasploitable2)**
2️⃣ **Web Application Penetration Testing (DVWA)**
3️⃣ **Social Engineering Penetration Testing (SEToolkit)**

All experiments were performed inside a **safe, isolated virtual environment** using Kali Linux and industry-standard tools.

---

# **📌 Objective**

The objective of this project is to identify, exploit, and analyze vulnerabilities across network, web, and human layers — replicating how real attackers achieve full system compromise.

---

# **📌 Features / What This Project Demonstrates**

### 🔹 **Network Pentesting (Metasploitable2)**

* Performed Nmap reconnaissance (SYN scan, service/version scan, aggressive scan).
* Identified vulnerable services including **vsftpd 2.3.4 backdoor**.
* Successfully exploited vsftpd using **Metasploit**, obtaining a **root shell**.
* Conducted post-exploitation enumeration (users, processes, ports, system files).

### 🔹 **Web Application Pentesting (DVWA)**

* Deployed DVWA using Docker for consistent testing.
* Set DVWA security level to **Low** to expose SQL Injection vulnerability.
* Performed SQL Injection:

  * Confirmed vulnerability using `'`.
  * Retrieved complete user records using `1' OR '1'='1`.
  * Extracted usernames and password hashes using UNION-based payloads.

### 🔹 **Social Engineering (Phishing) via SEToolkit**

* Launched SET → Social Engineering → Website Attack Vector → Credential Harvester.
* Cloned a real website (example: Facebook login page).
* Hosted phishing page locally using attacker IP.
* Captured victim credentials in real-time.

---

# **🧰 Tools & Technologies Used**

**Kali Linux**
**VirtualBox**
**Metasploitable2**
**Nmap**
**Metasploit Framework**
**DVWA (Damn Vulnerable Web Application)**
**Docker**
**SQL Injection Techniques**
**SEToolkit (Social Engineering Toolkit)**
**Linux Shell Commands**

---

# **📌 Project Architecture**

```
                +----------------+
                |   Kali Linux   |
                | (Attacker VM)  |
                +-------+--------+
                        |
                        | Host-Only / NAT Network
                        |
        +---------------+-------------------+
        |                                   |
+---------------+                   +---------------------+
| Metasploitable2 |                 | DVWA (Docker)       |
| (Network Target) |                | Web App Target      |
+------------------+                +---------------------+
                        |
                        |
                +---------------------+
                | SET Phishing Server |
                +---------------------+
```

---

# **📌 Penetration Testing Workflow**

1. **Reconnaissance** – Identify target details
2. **Scanning** – Enumerate open ports & services
3. **Vulnerability Identification**
4. **Exploitation**
5. **Post-Exploitation Analysis**

---

# **📌 Results**

### ✔ Network Testing

* vsftpd 2.3.4 backdoor exploited successfully
* Full root access obtained
* System enumeration completed

### ✔ Web Testing

* SQL Injection confirmed
* Extracted users & password hashes

### ✔ Social Engineering

* Credentials captured via phishing page

---

# **📌 Challenges Faced**

* Network adapter misconfiguration (NAT vs Host-Only)
* DVWA database setup errors
* SET phishing page inaccessible due to incorrect IP
* Slow internet during site cloning

---

# **📌 Future Enhancements**

* Add more attacks: XSS, Command Injection, File Upload bypass
* Automate scans with Nessus / OpenVAS
* Add firewall & IDS/IPS configuration
* Extend the lab into multi-machine corporate network simulation

---

# **📌 How to Run This Project**

### **1. Set up Virtual Machines**

* Install Kali Linux (Attacker)
* Install Metasploitable2 (Victim)
* Configure Host-Only Adapter for isolation

### **2. Network Pentesting**

```
nmap -sS <IP>
nmap -sV <IP>
nmap -A -T4 -p- <IP>
```

Use Metasploit to exploit vsftpd.

### **3. Web App Pentesting**

```
docker pull vulnerables/web-dvwa
docker run -d -p 80:80 vulnerables/web-dvwa
```

Navigate to DVWA → SQL Injection.

### **4. Social Engineering**

```
sudo setoolkit
```

Clone website → Host phishing page → Capture credentials.

---

# **📌 Contributors**

👤 **Sindhuja Arnepalli**
👤 **Guntur Ridhi**
👤 **Indu Kukatikonda**
👤 **Roda Chinthapalli**

---

# **📌 Supervisor**

**Dr. Sriramulu Bojjagani**
Department of Computer Science and Engineering
SRM University – AP

