# Cybersecurity Home Lab – Kali Linux & Metasploitable2

This project documents the creation and use of a self-contained penetration testing lab using VirtualBox, Kali Linux, and Metasploitable2. The lab focuses on **network reconnaissance and scanning** using Nmap in an isolated, safe environment.

---

## 🧭 Objectives

- Build a controlled virtual lab for security testing and experimentation  
- Practice network scanning and service enumeration with Nmap  
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
4. Verified network connectivity between <KALI_IP> and <TARGET_IP>

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
└── screenshots/
    ├── kali-desktop.png
    ├── nmap-results.png
```

---

## 📫 Contact
**Gabriel Kostman**  
📧 gjkostman@gmail.com  
🔗 https://www.linkedin.com/in/gabriel-kostman-20428136b/
