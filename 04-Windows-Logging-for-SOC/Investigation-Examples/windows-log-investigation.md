# Windows Log Investigation

**Platform:** TryHackMe  
**Room:** Windows Logging for SOC  
**Category:** SOC Investigation Practice

## 1. Investigation Overview

Windows logs provide valuable evidence about user activity, authentication attempts, process execution, and network connections.

In this investigation, I practiced analyzing Windows Security logs, Sysmon events, and PowerShell history to understand how suspicious activity can be detected and investigated.

## 2. Log Sources Used

| Log File | Purpose |
|---|---|
| `Practice-Security.evtx` | Authentication and user-management investigation |
| `Practice-Sysmon.evtx` | Process, file, and network activity investigation |
| PowerShell History | Review commands executed by Windows users |

## 3. Authentication Investigation

**Log Source:** Windows Security Log

**Event IDs:**
- `4624` – Successful Logon
- `4625` – Failed Logon

### Investigation Steps

1. Open `Practice-Security.evtx` in Event Viewer.
2. Filter for Event ID `4625`.
3. Identify suspicious failed login attempts.
4. Investigate the source IP address and targeted user account.
5. Filter for Event ID `4624`.
6. Identify the successful RDP login using Logon Type `10`.
7. Record the Logon ID for further investigation.

### Findings

| Investigation Detail | Result |
|---|---|
| Source IP performing brute force | `10.10.53.248` |
| Target workstation | `THM-PC` |
| Compromised user account | `Administrator` |
| Malicious RDP Logon Type | `10` |
| Malicious RDP Logon ID | `0x183C36D` |

## 4. User Management Investigation

**Log Source:** Windows Security Log

**Event IDs:**
- `4720` – User Account Created
- `4732` – Member Added to Security Group

### Investigation Steps

1. Continue analyzing `Practice-Security.evtx`.
2. Filter for Event ID `4720`.
3. Identify the account created after the suspicious RDP login.
4. Filter for Event ID `4732`.
5. Identify the privileged groups to which the new account was added.
6. Compare the Subject Logon ID with the previously identified malicious RDP session.

### Findings

| Investigation Detail | Result |
|---|---|
| Newly created account | `svc_sysrestore` |
| Privileged groups | `Backup Operators`, `Remote Desktop Users` |
| Logon ID correlation | Yes — `0x183C36D` |

## 5. Sysmon Process Investigation

**Log Source:** Sysmon Operational Log  
**Event ID:** `1` – Process Creation

### Investigation Steps

1. Open `Practice-Sysmon.evtx`.
2. Review Event ID `1`.
3. Identify the browser process used by Sarah.
4. Identify the file downloaded through the browser.
5. Investigate related Sysmon events to identify the download URL.
6. Review the process information and parent process details.

### Findings

| Investigation Detail | Result |
|---|---|
| Browser used | Google Chrome |
| Downloaded file | `C:\Users\sarah.miller\Downloads\ckjg.exe` |
| Download URL | `http://gettsveriff.com/bgj3/ckjg.exe` |

## 6. Sysmon File and Network Investigation

**Relevant Event IDs:**
- `3` – Network Connection
- `11` – File Creation
- `13` – Registry Value Set
- `22` – DNS Query

### Investigation Steps

1. Identify the downloaded malware process.
2. Record its Process ID.
3. Search for other Sysmon events with the same Process ID.
4. Identify the file created by the malware for persistence.
5. Investigate its network connections.
6. Identify the Command and Control (C2) server IP address and port.
7. Review DNS events to identify the domain associated with the malicious IP.

### Findings

| Investigation Detail | Result |
|---|---|
| Persistence file | `ckjg.exe` |
| C2 server IP and port | `193.46.217.4:7777` |
| Associated domain | `hkfasfsafg.click` |

## 7. PowerShell History Investigation

### Investigation Steps

1. Locate the Administrator's PowerShell history file.
2. Open `ConsoleHost_history.txt`.
3. Identify the first PowerShell command executed.
4. Check the file Properties to investigate the date of the first command.
5. Review other local users' PowerShell history files.
6. Search for the flag stored in the history.

### Findings

| Investigation Detail | Result |
|---|---|
| First PowerShell command | `Get-ComputerInfo` |
| First command date | May 18, 2025 |
| TryHackMe flag | `[REDACTED]` |

## 8. Investigation Lessons

Through this practical exercise, I learned:

- How to investigate brute-force activity using Event IDs `4625` and `4624`.
- How to identify suspicious account creation and privileged group membership changes.
- How to correlate authentication events using Logon ID.
- How to investigate process execution using Sysmon Event ID `1`.
- How to correlate file and network activity using Process ID.
- How to investigate PowerShell commands through command history.

## 9. Conclusion

This investigation helped me understand how SOC analysts use multiple Windows log sources to reconstruct suspicious activity and identify potential attack behavior.

It also strengthened my understanding of event correlation, endpoint monitoring, authentication analysis, and incident investigation.

**Status:** Practice investigation completed as part of TryHackMe Windows Logging for SOC.

*Learning by investigating. Building practical SOC Analyst skills one lab at a time.*
