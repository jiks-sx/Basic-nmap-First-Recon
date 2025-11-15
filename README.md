🛡️ What the Project Is About
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


>***Same as Kali-Linux***

># kali Linux :

<img width="2872" height="1772" alt="Screenshot 2025-11-15 103153" src="https://github.com/user-attachments/assets/837762a7-c028-41b4-89b7-977759cda358" />

<img width="2879" height="1638" alt="Screenshot 2025-11-15 103208" src="https://github.com/user-attachments/assets/c383cd02-fb0f-45ae-b069-b4cda5ae21f6" />

<img width="2879" height="1556" alt="Screenshot 2025-11-15 103235" src="https://github.com/user-attachments/assets/341b31ac-caf9-496b-86d3-ad78b094bcf9" />

![WhatsApp Image 2025-11-15 at 19 28 15_bd3d2651](https://github.com/user-attachments/assets/d65c5fad-2849-4b79-a874-61526f435494)


># Metasploitable2 :

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


***What it does:*** Sends ping requests to see which machines respond.

***Why it matters:*** Identifies “live hosts” — the starting point for deeper analysis.

# 3. Port Scanning & Service Enumeration
Command: nmap -sS -sV -O <target-ip>

***-sS →*** Stealth scan (SYN scan, less likely to be detected).

***-sV →*** Detects service versions (e.g., Apache 2.4.49).

***-O →*** OS detection.

>***Command: nmap --script=banner <target-ip>***

![WhatsApp Image 2025-11-15 at 19 28 17_1130376c](https://github.com/user-attachments/assets/e1657928-712f-4cde-94f4-9480a2c4726f)


***Grabs banners*** (text info services often reveal, like “Welcome to FTP server v2.3”).

>Why it matters:

***Open ports =*** entry points.

***Service versions =*** tell you if software is outdated and vulnerable.

***OS detection =*** helps attackers tailor exploits.

## 4. Vulnerability Detection
>***Command: nmap --script vuln <target-ip>***


![WhatsApp Image 2025-11-15 at 19 28 20_0bad6eb5](https://github.com/user-attachments/assets/4b834782-8752-474a-9443-1f64eb031c4e)



![WhatsApp Image 2025-11-15 at 19 28 20_1e6fa8e1](https://github.com/user-attachments/assets/2e63846c-f558-4a99-903b-ca95b02e8299)


![WhatsApp Image 2025-11-15 at 19 28 20_369a5531](https://github.com/user-attachments/assets/512d3381-3a55-4588-9c39-206d45b77da7)


![WhatsApp Image 2025-11-15 at 19 28 20_65b78bc4](https://github.com/user-attachments/assets/c6638326-fdf9-46c5-a381-196111b7aab3)


![WhatsApp Image 2025-11-15 at 19 28 20_6cc6b478](https://github.com/user-attachments/assets/210201bf-2c75-4cf1-830e-580911d3886b)


![WhatsApp Image 2025-11-15 at 19 28 20_a5232aec](https://github.com/user-attachments/assets/b57d491c-4ec1-41f4-a11c-2d8c64fdc710)


>Example scripts:

***ftp-anon →*** Checks if FTP allows anonymous login.

***smb-enum-shares →*** Lists shared folders on Windows machines.

***http-title →*** Grabs webpage titles.

>***Why it matters: Automates the discovery of known weaknesses. If Nmap finds “Apache 2.4.49” and you know it’s vulnerable to CVE-2021-41773, that’s a direct attack vector.***


