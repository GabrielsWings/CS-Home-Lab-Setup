# Metasploitable2 Reconnaissance & Vulnerability Analysis
**Target:** Metasploitable2  
**Environment:** Kali Linux

---

## 📍 01 - Initial Nmap Scan
**Objective:** Identify open ports and services on the target machine.

### 🔧 Command Used
```bash
nmap -sS -sV -T4 <192.168.56.102>
```

🧾 Example Output

PORT     STATE SERVICE     VERSION
21/tcp   open  ftp         vsftpd 2.3.4
22/tcp   open  ssh         OpenSSH 4.7p1
23/tcp   open  telnet      Linux telnetd
80/tcp   open  http        Apache 2.2.8
139/tcp  open  netbios-ssn Samba smbd 3.X
445/tcp  open  netbios-ssn Samba smbd 3.X


📝 Notes
FTP (21): Allows anonymous login — potential upload/download access

SSH (22): Available for brute-force testing

HTTP (80): Apache 2.2.8 — known vulnerabilities

Samba (139/445): Potential for remote code execution (RCE)

## 🔍 02 - Service Enumeration
Objective: Collect detailed service-level data to identify potential attack vectors.

### 📁 FTP Enumeration

```bash
ftp <192.168.56.102>
```

Anonymous login successful

Able to upload/download files — possible foothold

## 🌐 HTTP Enumeration
```bash
nikto -h <192.168.56.102>
```

Discovered default pages

Detected known vulnerabilities in Apache 2.2.8

## 🔐 SSH Enumeration
```bash
ssh -v <192.168.56.102>
```

Extracted version info for potential exploit matching

### 🛡️ 03 - Vulnerability Scanning
Objective: Identify known vulnerabilities using automated tools.

## 🔧 Nmap Vulnerability Script
```bash
nmap --script vuln <192.168.56.102>
```
🧾 Key Findings
vsftpd 2.3.4: Backdoor vulnerability (shell access possible)

Samba 3.X: Remote Code Execution (RCE) potential

Apache 2.2.8: Directory traversal & other exploits

### 📚 04 - Scan Notes & Next Steps
Objective: Summarize observations and plan the exploitation phase.

Prioritized Services for Exploitation
FTP: vsftpd backdoor

Samba: RCE vulnerability

Apache: Directory traversal
