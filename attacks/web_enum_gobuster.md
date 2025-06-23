# Web Enumeration using Gobuster

## 🧠 Objective

Enumerate hidden directories and pages on the target web server using `gobuster`.

---

## 🖥️ Target Info

- **Target IP**: 192.168.56.102
- **Service**: HTTP (Port 80)
- **Tool Used**: `gobuster`
- **Wordlist**: `/usr/share/wordlists/dirb/common.txt`

---

## 🔍 Step 1: Basic Directory Scan
### Command:
```bash
gobuster dir -u http://192.168.56.102 -w /usr/share/wordlists/dirb/common.txt
```
### 🔹 Result:
/index.html          (Status: 200)
/admin               (Status: 301)
/uploads             (Status: 200)
/backup              (Status: 403)


📝 Notes
/admin is accessible and may lead to an admin panel.
/uploads might allow file upload or contain sensitive files.
/backup exists but is restricted (403) — possibly interesting.
Consider brute-forcing deeper paths using recursive scanning.

+ Additional Flags
You can add useful flags to enhance results:
gobuster dir -u http://192.168.56.102 -w /usr/share/wordlists/dirb/common.txt -x php,txt,html -t 50
-x: search for specific extensions (e.g., .php)
-t: number of threads (speed up)

🔚 Conclusion
The HTTP service on the target reveals several interesting directories that could be further investigated or exploited.
Next steps could include:
Attempt access to /admin
Look inside /uploads for exposed files
Analyze /backup using LFI or bypass techniques
