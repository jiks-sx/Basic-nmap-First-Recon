
# 🛡️ What's the Project About 🛡️
This is a cybersecurity learning project. The goal is to teach **Students** how to use a tool called Nmap to explore and analyze computer networks. Think of Nmap as a "radar scanner" for computers — it helps you see which machines are online, what services they’re running, and whether they might have weaknesses.

><mark>**Which computers are online**</mark>

><mark>**What services (like websites, FTP servers, etc.) they are running**</mark>

><mark>**What vulnerabilities (weak points) they might have**</mark>

The goal is to practice ethical hacking — testing systems in a safe environment to understand how attackers might exploit them, and how to defend against those attacks.
# Basic-nmap-First-Recon
This repository documents an ethical, lab‑based reconnaissance exercise using Nmap to discover hosts, map open ports, enumerate services and OS fingerprints, and run non‑intrusive vulnerability checks via NSE scripts. All activities are confined to a local virtual lab.
# Objectives
Learn how scanning and enumeration (finding details about computers) are used in ethical hacking (testing systems to make them safer).

Practice using Nmap commands and its scripting engine (NSE).

Understand how to read scan results and spot possible vulnerabilities (weak points hackers could exploit).
# Prerequisites
**Software:** VirtualBox/VMware, Kali Linux VM, Metasploitable2/DVWA VM or container.

**Access:** Host‑only network configured; ability to run Nmap scans inside Kali.

**Knowledge:** Basic TCP/IP, subnetting, and Linux terminal usage.

# Step-by-Step Breakdown
>1. Set Up the Lab Environment

Use **VirtualBox** or **VMware** to create a safe, isolated test network.

>Machines:

**Attacker machine** → Kali Linux (penetration testing OS).

**Target machine** → Metasploitable2 or DVWA (deliberately vulnerable systems).

Why? → Safe practice environment where you can test without harming real systems.

# 1. Lab Setup: Kali Linux in VirtualBox/VMware

To replicate this project, you need a safe lab environment.  
We use **Kali Linux** (attacker machine) and **Metasploitable2/DVWA** (target machine).

Kali Linux is a hacking toolset, Metasploitable2 is a vulnerable target, and VMware is the virtual lab where you run them. Together, they form a powerful ethical hacking practice environment.

# How They Work Together

- You install VMware on your laptop.
- Inside VMware, you run Kali Linux as your attacker machine.
- You also run Metasploitable2 as your vulnerable target.
- Then, you use tools like Nmap or Metasploit from Kali to find and exploit weaknesses in Metasploitable2.
This setup is perfect for learning ethical hacking, OSINT, and penetration testing in a legal, controlled environment.



### Download For Windows

1.VirtualBox : Download From Oracle Site 

LInk : https://www.virtualbox.org

2.VMware Workstation pro : Download From Broadcom Support Portal 

Link : https://www.broadcom.com/

### 1.2. Target Machine
Use **Metasploitable2** or **DVWA (Damn Vulnerable Web App)** as the vulnerable target system.

Link : https://sourceforge.net/projects/metasploitable2/

### Installation Guides
>Step 1: Host

Install VirtualBox or VMware Workstation/Player on your host machine (Windows, Linux, or macOS).

# In VMware :

<img width="2877" height="1664" alt="Screenshot 2025-11-15 102916" src="https://github.com/user-attachments/assets/654522cd-b999-41d0-8f48-b9d7aacbd1f1" />


<img width="1839" height="1110" alt="Screenshot 2025-11-15 102937" src="https://github.com/user-attachments/assets/64647e99-d3ff-41a9-a89b-c8b035df9a40" />


<img width="1046" height="709" alt="Screenshot 2025-11-15 103057" src="https://github.com/user-attachments/assets/54076d8e-af40-4910-aefa-a32069945940" />

>## ***ADMIN OR PASSWORD IS BOTH :- msfadmin*** <<<


>***Same as Kali-Linux***

># kali Linux :


>***Kali Linux – The Attacker Machine***
- What it is: A Debian-based Linux distribution designed for penetration testing and ethical hacking.
- Purpose: Comes preloaded with 600+ tools like Nmap, Burp Suite, Metasploit, Wireshark, etc.
- Use case: You use Kali to scan, exploit, and analyze other systems.
- Who uses it: Ethical hackers, red teamers, cybersecurity students, and professionals.
- Runs on: Can be installed directly or run inside a virtual machine like VMware or VirtualBox.




<img width="2872" height="1772" alt="Screenshot 2025-11-15 103153" src="https://github.com/user-attachments/assets/837762a7-c028-41b4-89b7-977759cda358" />


<img width="2879" height="1638" alt="Screenshot 2025-11-15 103208" src="https://github.com/user-attachments/assets/c383cd02-fb0f-45ae-b069-b4cda5ae21f6" />


<img width="2879" height="1556" alt="Screenshot 2025-11-15 103235" src="https://github.com/user-attachments/assets/341b31ac-caf9-496b-86d3-ad78b094bcf9" />


![WhatsApp Image 2025-11-15 at 19 28 15_bd3d2651](https://github.com/user-attachments/assets/d65c5fad-2849-4b79-a874-61526f435494)

>## ***Deafult Kali's Username or Password :- Kali***


># Metasploitable2 :

- What it is: A deliberately insecure Linux virtual machine created by Rapid7.
- Purpose: Acts as a practice target for penetration testing tools like Metasploit.
- Use case: You attack Metasploitable2 from Kali to learn how real-world vulnerabilities work.
- Contains: Vulnerable services like FTP, SSH, MySQL, Tomcat, and more.
- Runs on: Must be run inside a virtual machine (like VMware or VirtualBox).




<img width="2879" height="1785" alt="Screenshot 2025-11-15 102956" src="https://github.com/user-attachments/assets/18b6c0e7-97a3-42d7-83fe-ed86bac7fa93" />


<img width="888" height="545" alt="Screenshot 2025-11-15 104305" src="https://github.com/user-attachments/assets/0dba9a42-658b-4aa7-8b9d-e34a29f47b41" />



### 🛠️ Tools: Nmap & NSE
>***Nmap (Network Mapper):*** A powerful open-source tool for network discovery and security auditing.

>***NSE (Nmap Scripting Engine):*** Lets you run scripts to automate tasks like vulnerability detection, banner grabbing, or brute force attempts.

***Why Nmap?***

>It’s lightweight, fast, and widely used by professionals.

>It can detect operating systems, services, and even misconfigurations.

# 2. Network Discovery

##Find Live Computers

Run nmap -sn <target-subnet> → this checks which machines are online.


Command: nmap -sn <target-subnet>

![WhatsApp Image 2025-11-15 at 21 25 17_faf79a0a](https://github.com/user-attachments/assets/b42e9f1e-ebb0-481a-8c75-e5414269c1f0)

Command: nmap -sS -sV -O <target-ip>

***-sS →*** Stealth scan (SYN scan, less likely to be detected).

***-sV →*** Detects service versions 

***-O →*** OS detection.


***What it does:*** Sends ping requests to see which machines respond.

***Why it matters:*** Identifies “live hosts” — the starting point for deeper analysis.

# 3. Port Scanning & Service Enumeration

>Port Scanning is the process of checking which ports on a target system are open, closed, or filtered.

Every port runs a specific service (FTP, SSH, HTTP, etc.).

***Because open ports = possible entry points for an attack***

After finding open ports, the next step is ***Service Enumeration.***

>Service Enumeration means gathering more details about the service running on those ports.

Example:
Port 21 is open → but which FTP server? What version? Is it vulnerable?

Enumeration tells us:

Service name (FTP, SSH, HTTP, SMB…)

Service version (e.g., vsftpd 2.3.4)

Operating system details

Available shares, users, directories

***Known vulnerabilities (CVE)***


>***Command: nmap --script=banner <target-ip>***

![WhatsApp Image 2025-11-15 at 19 28 17_1130376c](https://github.com/user-attachments/assets/e1657928-712f-4cde-94f4-9480a2c4726f)

>Example scripts:

***ftp-anon →*** Checks if FTP allows anonymous login.

***smb-enum-shares →*** Lists shared folders on Windows machines.

***http-title →*** Grabs webpage titles.

>***Why it matters: Automates the discovery of known weaknesses. If Nmap finds “Apache 2.4.49” and you know it’s vulnerable to CVE-2021-41773, that’s a direct attack vector.***


***Grabs banners*** (text info services often reveal, like “Welcome to FTP server v2.3”).

>Why it matters:

***Open ports =*** entry points.

***Service versions =*** tell you if software is outdated and vulnerable.

***OS detection =*** helps attackers tailor exploits.

## 4. Vulnerability Detection
>***Command: nmap --script vuln <target-ip>***


![WhatsApp Image 2025-11-15 at 19 28 20_0bad6eb5](https://github.com/user-attachments/assets/4b834782-8752-474a-9443-1f64eb031c4e)

>***1. FTP (21/tcp) – VULNERABLE***

vsFTPd 2.3.4 Backdoor (CVE-2011-2523)

This FTP version contains a malicious backdoor inserted by an attacker in 2011.

When someone logs in with a username containing “:)”, the server opens a shell on port 6200.

This shell gives root access to the system.


>Why dangerous?

Complete system takeover → Full Control of the machine.


---

>***2. SSH (22/tcp)***

SSH is open but no vulnerability detected in your screenshot.
(Only port shows “open ssh”.)


---

>***3. Telnet (23/tcp)***

Telnet is open. Telnet is insecure but Nmap didn't detect a specific "vulnerability".


---

>***4. SMTP (25/tcp)***

Nmap checked if the SMTP server is Exim, but result is:

NOT VULNERABLE

So SMTP is safe from that specific exploit.


---

>***5. SSL (443/tcp or service using SSL) – MULTIPLE VULNERABILITIES***

Your scan shows multiple SSL/TLS weaknesses:



![WhatsApp Image 2025-11-15 at 19 28 20_1e6fa8e1](https://github.com/user-attachments/assets/2e63846c-f558-4a99-903b-ca95b02e8299)

>**Anonymous Diffie-Hellman Key Exchange – VULNERABLE**

This allows an attacker to perform MITM (Man-in-the-Middle) attacks.

Impact:

Traffic can be intercepted and decrypted.


---

>**Logjam Attack – VULNERABLE (CVE-2015-4000)**

Weak DH group used → attacker can break encryption.

Impact:

Session keys can be stolen.


---

>**POODLE Attack – SSLv3 (CVE-2014-3566)**

Old SSL protocol vulnerable to padding-oracle attack.

Impact:

Cookies and session data can be stolen.


---

>>***. HTTP (80/tcp) – MULTIPLE VULNERABILITIES***

Your target (Metasploitable II / Mutillidae) is intentionally vulnerable.


---

>a) Slowloris Attack – LIKELY VULNERABLE

Slowloris holds connections open to exhaust server resources.

Impact:

Website can be taken down using DoS attack.


---

>b) DOM-Based XSS – Not Found

Nmap could not find a DOM-based XSS in this scan.


---

>c) HTTP TRACE Enabled

Server allows TRACE method → possible Cross-site tracing.


---

>d) SQL Injection – Enabled

Nmap found many URLs vulnerable to SQL injection:

Example:

/index.php?page=home.php%27%20OR%20%271%27%3D%271

Impact:

Bypass login

Dump database

Gain admin access


![WhatsApp Image 2025-11-15 at 19 28 20_369a5531](https://github.com/user-attachments/assets/512d3381-3a55-4588-9c39-206d45b77da7)


![WhatsApp Image 2025-11-15 at 19 28 20_65b78bc4](https://github.com/user-attachments/assets/c6638326-fdf9-46c5-a381-196111b7aab3)


![WhatsApp Image 2025-11-15 at 19 28 20_6cc6b478](https://github.com/user-attachments/assets/210201bf-2c75-4cf1-830e-580911d3886b)


![WhatsApp Image 2025-11-15 at 19 28 20_a5232aec](https://github.com/user-attachments/assets/b57d491c-4ec1-41f4-a11c-2d8c64fdc710)


>***Here are the most dangerous because they affect the entire server, not just a website.***

>Major Issues in Result 

⚠️ Category	Problem	Risk

>>Open Ports	FTP, Telnet, SMB, VNC, MySQL exposed	------  Critical
Weak

>>SSL/TLS	Weak Diffie-Hellman Group (1024-bit)	------  High

>>SSL POODLE (CVE-2014-3566)	SSL 3.0 padding attack	--------  High

>>SSL CCS Injection (CVE-2014-0224)	MITM session hijack	Critical
Old Services	Outdated Apache, OpenSSL	-------- High



---

>shows vulnerabilities that allow:

>Remote code execution

>Man-in-the-middle attacks

>Decrypting SSL traffic

>Hijacking secure sessions

>Gaining system-level access

# Vulnerability Scan Report

>Target: ***192.168.145.129***
>Scan Tool: ***Nmap (--script vuln)***
>Report Type: System-Level Vulnerabilities 


---

Summary

>A comprehensive Nmap vulnerability scan identified multiple critical security weaknesses on the target machine. These include outdated services, insecure configurations, exposed ports, and severe SSL/TLS vulnerabilities. If this system were exposed to any network, it could be compromised with minimal effort.


---

>***Open Ports and Services***

| Port      | Service        | Risk |
|-----------|----------------|------|
| 21/tcp    | FTP            | 🔴 High |
| 22/tcp    | SSH            | 🟡 Medium |
| 23/tcp    | Telnet         | 🔴 High |
| 25/tcp    | SMTP           | 🟡 Medium |
| 53/tcp    | DNS (Domain)   | 🟡 Medium |
| 80/tcp    | HTTP           | 🟢 Low |
| 111/tcp   | RPCBind        | 🔴 High |
| 139/tcp   | NetBIOS-SSN    | 🔴 High |
| 445/tcp   | Microsoft-DS   | 🔴 High |
| 512/tcp   | Exec           | 🔴 High |
| 513/tcp   | Login          | 🔴 High |
| 514/tcp   | Shell          | 🔴 High |
| 3306/tcp  | MySQL          | 🟡 Medium |
| 5432/tcp  | PostgreSQL     | 🟡 Medium |
| 5900/tcp  | VNC            | 🔴 High |
| 8009/tcp  | AJP13          | 🔴 High |
| 8080/tcp  | HTTP-Alt       | 🟡 Medium |

>Many services are outdated and exposed to the network, increasing the risk of remote exploitation.


---

>**SSL/TLS Vulnerabilities**

Weak Diffie-Hellman Group

State: Vulnerable

Uses a 1024-bit DH group, which is insecure.

Allows attackers to passively decrypt TLS traffic.



---

>**SSL POODLE (CVE-2014-3566)**

State: Vulnerable

Exploits SSL 3.0 padding behavior.

Can lead to decryption of session cookies and sensitive data.



---

>**TLS/SSL CCS Injection (CVE-2014-0224)**

State: Vulnerable (High Risk)

Enables a man-in-the-middle to hijack encrypted connections.

Can compromise login sessions and encrypted traffic.



---

Risk Level Overview

Category	Risk Level

System Exposure	Critical
SSL/TLS Weaknesses	Critical
Outdated Services	Critical
Web Application Issues	Medium



---

# Remediation (Fixes)

>***1. Secure Open Ports***

Close unused ports immediately (Telnet, FTP, SMB, RPC, VNC).

Replace insecure services:

FTP → SFTP

Telnet → SSH

SMTP: enable TLS


>Apply a firewall policy:

Deny all inbound traffic by default
Allow only required services (e.g., SSH)



---

>***2. Update Server Packages***

Update Apache, OpenSSL, MySQL, PostgreSQL, and Samba to latest versions.

Apply OS-level security patches.

Remove unnecessary packages.



---

>***3. Fix TLS/SSL Vulnerabilities***

Disable insecure protocols

Disable SSL 2.0, SSL 3.0, and TLS 1.0.

Allow only modern TLS versions:

TLS 1.2

TLS 1.3



Configure strong cipher suites

Disable weak ciphers (RC4, 3DES).

Enable strong elliptic-curve ciphers.


Use secure Diffie-Hellman parameters

Generate a 2048-bit or 4096-bit DH group.

Update server configuration.



---

>***4. Hardening Recommendations***

Enforce strong passwords and SSH key authentication.

Disable root login over SSH.

Restrict database access to local connections.

Configure Fail2ban or similar intrusion protection.

Enable regular system and vulnerability scanning.



---

# Final Conclusion

This vulnerability assessment confirms that the target system contains multiple critical security flaws that make it highly vulnerable to attack. The combination of outdated software, weak TLS configurations, exposed ports, and high-risk vulnerabilities poses a significant threat to confidentiality, integrity, and system availability.

The findings strongly indicate that this machine is likely a practice environment (e.g., Metasploitable or DVWA lab), but the vulnerabilities identified mirror real-world risks found in poorly secured production systems.

To secure the system, immediate remediation actions are required, including disabling insecure services, patching outdated components, and enforcing strong cryptographic configurations.

This concludes the final vulnerability report.





#Connect with Me : 
## 🔗 Connect With Me  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Profile-blue?logo=linkedin&style=for-the-badge)](https://www.linkedin.com/in/jitu-sah/)
