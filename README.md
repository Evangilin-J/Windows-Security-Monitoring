# 🛡️ Week 02 – Windows Security Monitoring

## 📌 Project Overview
This project focuses on **Windows Security Monitoring** using **Windows Event Viewer** and important **Windows Security Event IDs**. The goal is to understand how a SOC Analyst monitors Windows authentication, logon/logoff activity, account lockouts, local group enumeration, credential manager access, and privileged access events.

---

## 🎯 Objectives
* Understand Windows Event Viewer
* Monitor Windows Security Logs
* Learn important Security Event IDs
* Analyze successful and failed logon attempts
* Identify suspicious authentication and local group queries
* Understand account lockout and privileged logon events
* Build basic SOC monitoring and investigation skills

---

## 🛠️ Tools Used
* 🪟 Windows 10/11
* 📊 Windows Event Viewer
* 💻 PowerShell
* 🖥️ Windows Terminal
* ✂️ Snipping Tool
* 🌐 Git & GitHub

---

## 🔎 Important Windows Event IDs

| Event ID | Description |
| :--- | :--- |
| **4624** | Successful Logon |
| **4625** | Failed Logon |
| **4634** | Account Logoff |
| **4672** | Special Privileges Assigned to New Logon |
| **4740** | User Account Locked Out |
| **4798** | A user's local group membership was enumerated |
| **5379** | Credential Manager credentials were read |

---

## 🔍 Event Analysis

### 4624 – Successful Logon
Shows that a user successfully logged into Windows. 
* **Important fields analyzed:** Account Name, Logon Type, Logon ID, Workstation Name, Source Network Address, Date and Time.

### 4625 – Failed Logon
Shows an unsuccessful login attempt. This event is useful for detecting:
* Brute-force attempts
* Password spraying[cite: 4]
* Repeated authentication failures[cite: 4]
* Suspicious login activity[cite: 4]
* **Important fields:** Account Name, Failure Reason, Logon Type, Workstation Name, Source Network Address.

### 4634 – Account Logoff
Shows when a user account logs off from Windows. This can help SOC analysts understand user session activity and session duration.

### 4672 – Special Privileges Assigned
This event indicates that special privileges were assigned to a new logon session. It is useful for monitoring privileged account activity.
* **Important fields:** Account Name, Privileges, Logon ID, Date and Time.

### 4740 – User Account Locked Out
This event is related to account lockout activity. It helps investigate repeated failed authentication attempts and possible password attacks.
* **Important fields:** Target Account, Caller Computer Name, Date and Time.
> *Note: Event ID 4740 may not appear on a standalone Windows system because it is commonly associated with Active Directory/domain account lockouts.*

### 4798 – Local Group Membership Enumeration
This event tracks when a user or application queries local group memberships on the system, which can indicate local reconnaissance activity.

### 5379 – Credential Manager Credentials Read
This event tracks when stored credentials within the Windows Credential Manager are accessed or read.

---

## 🧪 Practical Investigation
During this project, Windows Event Viewer was used to:
1. Open **Windows Logs → Security**
2. Filter events using specific Event IDs
3. Open individual security events and view properties
4. Analyze event details and fields
5. Identify authentication and security-related information
6. Capture screenshots for documentation (`Screenshot-1` to `Screenshot-7`)
7. Record important findings

---

## 📸 Screenshots Collected
The following screenshots captured from the system are included in the project:
* `Screenshot-1.jpg` – Event Viewer Overview and Summary Dashboard[cite: 2]
* `Screenshot-2.jpg` – Windows Security Log Main View[cite: 3]
* `Screenshot-3.jpg` – Event ID 4625 (Failed Logon Details)[cite: 4]
* `Screenshot-4.jpg` – Event ID 4798 (Local Group Enumeration Details)[cite: 5]
* `Screenshot-5.jpg` – Event ID 4672 (Special Logon / Privileges Assigned)[cite: 6]
* `Screenshot-6.jpg` & `Screenshot-7.jpg` – Event ID 5379 (Credential Manager & Filter Settings)[cite: 7, 8]

---

## 📁 Project Structure
```text
week-02-windows-security-monitoring/
│
├── README.md
├── screenshots/
│   ├── Screenshot-1.jpg
│   ├── Screenshot-2.jpg
│   ├── Screenshot-3.jpg
│   ├── Screenshot-4.jpg
│   ├── Screenshot-5.jpg
│   ├── Screenshot-6.jpg
│   └── Screenshot-7.jpg
│
├── event-ids/
│   └── important-event-ids.txt
│
└── report/
    └── windows-security-monitoring-report.pdf
