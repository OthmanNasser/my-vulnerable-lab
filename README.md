# my-vulnerable-lab

A custom vulnerable lab setup for penetration testing practice using Kali Linux, Metasploitable2, and common attack tools.

---

## Lab Overview

This is a custom penetration testing lab designed for practicing offensive security skills in a safe local environment.

### Components:
- **Attacker Machine**: Kali Linux (2024.1)
- **Target Machine**: Metasploitable2 (Ubuntu 8.04)
- **Network**: Host-only (VirtualBox)

---

## Objectives

- Enumerate network services using tools like `nmap`, `gobuster`.
- Exploit known vulnerabilities in FTP, HTTP, and SSH.
- Practice privilege escalation techniques.
- Build and document repeatable attack scenarios.

---

## Tools Used

- Kali Linux tools: `nmap`, `hydra`, `sqlmap`, `burpsuite`, `msfconsole`, `gobuster`
- Custom scripts written in `bash` and `python`

---

## Lab Topology

  [ Kali Linux ]
        |
[ Host-only Network ]
        |
 [ Metasploitable2 ]


- IP (Kali): 192.168.56.101
- IP (Target): 192.168.56.102

---

## Attack Scenarios (coming soon)

Each attack will be documented in its own Markdown file inside `/attacks/` directory:

- [ ] FTP Anonymous Access
- [ ] vsftpd 2.3.4 Exploit
- [ ] Simple Web Enumeration with gobuster
- [ ] SQL Injection on Web App

 
