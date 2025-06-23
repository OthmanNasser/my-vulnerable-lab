# FTP Anonymous Access

## 🧠 Objective

Enumerate the target's FTP service to check if anonymous login is enabled and explore accessible files.

---

## 🖥️ Target Info

- **Target IP**: 192.168.56.102
- **Service**: FTP (Port 21)
- **Tool Used**: `ftp`, `nmap`, `searchsploit`

---

### 🔹 Step 1: Port Scan with Nmap

```bash
nmap -sV -p 21 192.168.56.102

### 🔹 Result:
21/tcp open  ftp     vsftpd 2.3.4


### 🔹 Step 2: Attempt Anonymous Login
ftp 192.168.56.102

Login:
Name: anonymous
Password: (press Enter)

Success: Logged in anonymously.


### 🔹 Step 3: List Files
ls

Output:
README.txt

Download file:
get README.txt


### 🔹 Step 4: Check for Known Vulnerabilities
searchsploit vsftpd 2.3.4

### 🔹 Result:
Exploit available for backdoor command execution.


📝 Notes
Anonymous login enabled = Misconfiguration.
Version 2.3.4 has a known backdoor vulnerability.
This could be exploited further using Metasploit.


🔚 Conclusion
The FTP service allows anonymous access, which reveals sensitive information and runs
a vulnerable version of vsftpd. This can lead to further compromise.
