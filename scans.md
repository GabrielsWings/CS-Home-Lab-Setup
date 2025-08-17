# Metasploitable2 Reconnaissance & Vulnerability Analysis
**Target:** Metasploitable2  
**Environment:** Kali Linux

---

## 📍 01 - Initial Nmap Scan
**Objective:** Identify open ports and services on the target machine.

### 🔧 Command Used
```bash
nmap -sS -sV -T4 <192.168.56.103>
```

🧾 Output

![image alt] (https://github.com/GabrielsWings/CS-Home-Lab-Setup/blob/756c95a3b4ab57180751060bb5dbf1a51d380d47/Initial%20nmap%20Scan.png)

### 📝 Notes
Lots of exposed services → this is a deliberately vulnerable machine.

FTP (21 & 2121): Both standard vsftpd and ProFTPD are running → good future targets for enumeration.

SSH (22): Available for logon / brute-force attempts.

Telnet (23): Legacy unencrypted protocol → usually insecure.

Apache (80 / 8180): Shows outdated versions (Apache 2.2.8 and Tomcat 1.1).

Samba (139 / 445): Known for remote code execution in older versions.

1524/tcp – bindshell: A root shell already bound to a port (intentional backdoor).

Multiple database services running (MySQL, PostgreSQL) → potential data exfiltration path.

VNC (5900): Possible unauthenticated access.

Overall → This system is highly vulnerable and contains several attack surfaces for future exploitation.

## ⚡ 02 – Aggressive Nmap Scan

Objective: Perform OS detection and gather additional details using default Nmap scripts.

### 🔧 Command Used
```bash
nmap -A 192.168.56.103
```
🧾 Output

<img width="802" height="698" alt="nmap -A" src="https://github.com/user-attachments/assets/3bde9b6b-8cb9-4879-82ef-ed46a53c7512" />

### 📝 Notes

OS detected as Linux kernel 2.6.x (outdated)

Host identified as metasploitable.localdomain

SMB scripts confirm Samba 3.0.20 (legacy version)

Message signing disabled → insecure configuration

Confirms target is a vulnerable Linux VM in the isolated lab

## 🛡️ 03 - Vulnerability Scan with Nmap Scripts
**Objective:** Identify known vulnerabilities using automated Nmap scripts.

### 🔧 Command Used
```bash
nmap --script vuln 192.168.56.103
```
🧾 Output

<img width="801" height="694" alt="nmap --script vuln" src="https://github.com/user-attachments/assets/6ff4185d-c553-43d6-be66-234ba73c0374" />

### 📝 Notes

FTP (21): vsFTPd 2.3.4 backdoor detected → exploitable root shell (CVE-2011-2523)

SSH / Telnet / SMTP / others: No immediate vulnerabilities flagged by this scan

Prioritize FTP for the exploitation phase with Metasploit
