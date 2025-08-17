# Cybersecurity Home Lab – Kali Linux & Metasploitable2

This project documents the creation and use of a self-contained penetration testing lab using **VirtualBox**, **Kali Linux**, and **Metasploitable2**. The environment simulates real-world attack scenarios in an isolated and legally safe environment.

---

## 🧭 Objectives

- Build a controlled virtual lab for security testing and experimentation  
- Practice reconnaissance, enumeration, and exploitation techniques  
- Utilize industry-standard tools such as **Nmap** and **Metasploit**  
- Create detailed technical documentation suitable for a professional portfolio

---

## 🖥️ Lab Architecture

```
[Host Machine]
│
├── VirtualBox
│   ├── Kali Linux (Attacker) – <192.168.56.101>
│   └── Metasploitable2 (Target) – <192.168.56.102>
│
└── Host-Only Network (Isolated)
```

---

## ⚙ Tools & Technologies
| Category           | Tools / Technologies                                  |
|--------------------|------------------------------------------------------|
| Networking         | Nmap, Wireshark, TCP/IP                               |
| Endpoint           | Kali Linux, Windows 11 (host), Metasploitable2        |
| SIEM               | (Planned) Splunk / Wazuh                              |
| Offensive Tools    | Metasploit Framework, Burp Suite                      |

---

## 🔧 Setup Summary
1. **VirtualBox** installed on host system  
2. **Kali Linux** and **Metasploitable2** VMs imported  
3. **Host-Only Adapter** configured for isolated communication  
4. Verified network connectivity between <KALI_IP> and <TARGET_IP>

---

## 📌 Penetration Testing Workflow
| Phase              | Description |
|-------------------|-------------|
| **Scanning**       | Identify open ports using `nmap` |
| **Enumeration**    | Gather service information and version details |
| **Exploitation**   | Launch targeted exploits using Metasploit |
| **Post-Exploitation** | Access target system and collect artifacts |

---

## 📂 Repository Structure
```
cybersecurity-homelab/
│
├── setup/
│   ├── virtualbox-setup.md
│   ├── kali-setup.md
│   ├── metasploitable-setup.md
│   └── networking.md
│
├── scans/
│   ├── nmap-initial.md
│   ├── service-discovery.md
│
├── exploits/
│   ├── msfconsole-walkthrough.md
│
└── screenshots/
    ├── kali-desktop.png
    ├── nmap-results.png
    └── exploit-success.png
```

---

## 📫 Contact
**Gabriel Kostman**  
📧 gjkostman@gmail.com  
🔗 https://www.linkedin.com/in/gabriel-kostman-20428136b/
