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

## 🔮 Next Steps

Perform service-specific enumeration (FTP, SSH, HTTP)

Explore safe exploitation in a fully isolated lab

Document post-exploitation findings
