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

### 🛠️ Tools: Nmap & NSE
>***Nmap (Network Mapper):*** A powerful open-source tool for network discovery and security auditing.

>***NSE (Nmap Scripting Engine):*** Lets you run scripts to automate tasks like vulnerability detection, banner grabbing, or brute force attempts.

***Why Nmap?***

>It’s lightweight, fast, and widely used by professionals.

>It can detect operating systems, services, and even misconfigurations.

# 2. Network Discovery
Command: nmap -sn <target-subnet>

***What it does:*** Sends ping requests to see which machines respond.

***Why it matters:*** Identifies “live hosts” — the starting point for deeper analysis.

# 3. Port Scanning & Service Enumeration
Command: nmap -sS -sV -O <target-ip>

***-sS →*** Stealth scan (SYN scan, less likely to be detected).

***-sV →*** Detects service versions (e.g., Apache 2.4.49).

***-O →*** OS detection.

>***Command: nmap --script=banner <target-ip>***

***Grabs banners*** (text info services often reveal, like “Welcome to FTP server v2.3”).

>Why it matters:

***Open ports =*** entry points.

***Service versions =*** tell you if software is outdated and vulnerable.

***OS detection =*** helps attackers tailor exploits.

## 4. Vulnerability Detection
>***Command: nmap --script vuln <target-ip>***

>Example scripts:

***ftp-anon →*** Checks if FTP allows anonymous login.

***smb-enum-shares →*** Lists shared folders on Windows machines.

***http-title →*** Grabs webpage titles.

>***Why it matters: Automates the discovery of known weaknesses. If Nmap finds “Apache 2.4.49” and you know it’s vulnerable to CVE-2021-41773, that’s a direct attack vector.***


