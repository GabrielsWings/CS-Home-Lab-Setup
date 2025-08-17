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

![Initial Nmap Scan](../screenshots/nmap-initial-scan.png)

📝 Notes
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

⚡ 02 – Aggressive Nmap Scan

Objective: Perform OS detection and gather additional details using default Nmap scripts.

🔧 Command Used
```bash
nmap -A 192.168.56.103
```
🧾 Output

AC Address: 08:00:27:43:6F:7C (PCS Systemtechnik/Oracle VirtualBox virtual NIC)
Device type: general purpose
Running: Linux 2.6.X
OS CPE: cpe:/o:linux:linux_kernel:2.6
OS details: Linux 2.6.9 - 2.6.33
Network Distance: 1 hop
Service Info: Hosts:  metasploitable.localdomain, irc.Metasploitable.LAN; OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

Host script results:
| smb-os-discovery: 
|   OS: Unix (Samba 3.0.20-Debian)
|   Computer name: metasploitable
|   NetBIOS computer name: 
|   Domain name: localdomain
|   FQDN: metasploitable.localdomain
|_  System time: 2025-08-17T17:27:58-04:00
|_clock-skew: mean: 1h00m00s, deviation: 2h00m00s, median: 0s
|_smb2-time: Protocol negotiation failed (SMB2)
| smb-security-mode: 
|   account_used: guest
|   authentication_level: user
|   challenge_response: supported
|_  message_signing: disabled (dangerous, but default)
|_nbstat: NetBIOS name: METASPLOITABLE, NetBIOS user: <unknown>, NetBIOS MAC: <unknown> (unknown)


📸 Screenshot: Take a screenshot of the output section showing the OS detection and Nmap script results (e.g. “OS details: Linux 2.6.9 – 2.6.33”, “smb-os-discovery”, etc.)

📝 Takeaways

OS detected as Linux kernel 2.6.x (outdated)

Host identified as metasploitable.localdomain

SMB scripts confirm Samba 3.0.20 (legacy version)

Message signing disabled → insecure configuration

Confirms target is a vulnerable Linux VM in the isolated lab
