# Cybersecurity Home Lab – Kali Linux & Metasploitable2

This project documents the creation and use of a self-contained penetration testing lab using VirtualBox, Kali Linux, and Metasploitable2. The lab focuses on **network reconnaissance and scanning** using Nmap in an isolated, safe environment.

---

## 🧭 Objectives

- Build a controlled virtual lab for security testing and experimentation  
- Practice network scanning and OS/service detection with Nmap  
- Create detailed technical documentation suitable for a professional portfolio

---

## 🖥️ Lab Architecture

```
[Host Machine]
│
├── VirtualBox
│ ├── Kali Linux (Attacker) – <192.168.56.101>
│ └── Metasploitable2 (Target) – <192.168.56.103>
│
└── Host-Only Network (Isolated)
```

---

## ⚙ Tools & Technologies
| Category           | Tools / Technologies            |
|--------------------|--------------------------------|
| Virtualization     | VirtualBox                     |
| Attacker OS        | Kali Linux                     |
| Target OS          | Metasploitable2                |
| Reconnaissance     | Nmap                           |

---

## 🔧 Setup Summary
1. **VirtualBox** installed on host system  
2. **Kali Linux** and **Metasploitable2** VMs imported  
3. **Host-Only Adapter** configured for isolated communication  
4. Verified network connectivity between Kali Linux and Metasploitable2

---

## 📂 Repository Structure
```
cybersecurity-homelab/
│
├── setup/
│ ├── virtualbox-setup.md
│ ├── kali-setup.md
│ ├── metasploitable-setup.md
│ └── networking.md
│
├── scans/
│ ├── 01-nmap-initial.md
│ ├── 02-nmap-aggressive.md
│ └── 03-nmap-vuln-scan.md
│
└── screenshots/
├── nmap-initial.png
├── nmap-aggressive.png
└── nmap-vuln-scan.png
```

---

## 📫 Contact
**Gabriel Kostman**  
📧 gjkostman@gmail.com  
🔗 https://www.linkedin.com/in/gabriel-kostman-20428136b/
