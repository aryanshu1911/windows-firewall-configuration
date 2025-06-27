# 🔒 Task: Setup and Use a Firewall on Windows

## 📌 Objective
Configure and test basic firewall rules to allow or block traffic using **Windows Defender Firewall**.

---

## 🧰 Tools Used
- **Windows Defender Firewall (Advanced Security)**
- **Command Prompt**
- **Telnet Client**

---

## 🛠️ Steps Performed

### 1. Access Firewall Configuration
Opened **Windows Defender Firewall with Advanced Security** via the Start menu.

### 2. Viewed Existing Rules
Navigated to **Inbound Rules** to view the current firewall configuration.

### 3. Created Rule to Block Port 23 (Telnet)
- New Rule → **Type:** Port  
- **Protocol:** TCP  
- **Port:** 23  
- **Action:** Block the connection  
- **Applied to:** Domain, Private, Public  
- **Rule Name:** `Block Telnet Port 23`

### 4. Installed Telnet Client
Enabled via Command Prompt:
```cmd
dism /online /Enable-Feature /FeatureName:TelnetClient
````

### 5. Tested the Block Rule

Executed the following in Command Prompt:

```cmd
telnet localhost 23
```

**Result:**
`'Could not open connection to the host, on port 23: Connect failed'`
✅ This confirms **port 23 was successfully blocked**.

### 6. Created Rule to Allow Port 22 (SSH)

* New Rule → **Type:** Port
* **Protocol:** TCP
* **Port:** 22
* **Action:** Allow the connection
* **Applied to:** Domain, Private, Public
* **Rule Name:** `Allow SSH Port 22`

### 7. Removed Test Rule

Deleted the `Block Telnet Port 23` rule from Inbound Rules to restore the original firewall state.

---

## 🧾 Summary

Windows Defender Firewall uses rule-based control to allow or block traffic by port, program, or IP address.

In this task:

* A rule was created to **block Telnet (port 23)**, an insecure protocol.
* Another rule was created to **allow SSH (port 22)**, a secure and commonly used protocol for remote access.
* The firewall successfully **blocked unauthorized access** and **permitted secure connections**, showing how firewall rules are used to manage and filter network traffic effectively.

---
