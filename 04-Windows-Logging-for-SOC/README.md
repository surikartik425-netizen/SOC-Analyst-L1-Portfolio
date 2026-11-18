# Windows Logging for SOC

**Platform:** TryHackMe
**Learning Path:** SOC Level 1 → Windows Security Monitoring
**Room:** Windows Logging for SOC

## Overview

This room focuses on Windows logging and security monitoring. It provides practical experience in understanding Windows event logs, analyzing authentication activity, monitoring processes with Sysmon, and investigating PowerShell commands.

As part of my SOC Analyst Level 1 learning journey, I explored how Windows logs help security analysts identify suspicious activities, investigate incidents, and understand attacker behavior.

## Learning Objectives

- Understand Windows Event Logs and how to use Event Viewer.
- Analyze successful and failed authentication events.
- Identify suspicious user account creation and group membership changes.
- Understand process monitoring using Sysmon.
- Investigate file creation, network connections, and DNS queries.
- Understand PowerShell history and command logging.
- Correlate events using Logon ID and Process ID.

## Topics Covered

| Task   | Topic                         |
| ------ | ----------------------------- |
| Task 1 | Introduction                  |
| Task 2 | What Is Logged                |
| Task 3 | Security Log: Authentication  |
| Task 4 | Security Log: User Management |
| Task 5 | Sysmon: Process Monitoring    |
| Task 6 | Sysmon: Files and Network     |
| Task 7 | PowerShell: Logging Commands  |
| Task 8 | Conclusion                    |

## Important Windows Event IDs

| Event ID  | Description                        |
| --------- | ---------------------------------- |
| 4624      | Successful Logon                   |
| 4625      | Failed Logon                       |
| 4720      | User Account Created               |
| 4722      | User Account Enabled               |
| 4723      | User Password Changed              |
| 4724      | User Password Reset                |
| 4725      | User Account Disabled              |
| 4726      | User Account Deleted               |
| 4732      | Member Added to Security Group     |
| 4733      | Member Removed from Security Group |
| 4738      | User Account Changed               |
| 4688      | Process Creation                   |
| Sysmon 1  | Process Creation                   |
| Sysmon 3  | Network Connection                 |
| Sysmon 11 | File Creation                      |
| Sysmon 13 | Registry Value Set                 |
| Sysmon 22 | DNS Query                          |

## Tools and Technologies

- Windows Event Viewer
- Windows Security Logs
- Sysmon
- PowerShell
- EVTX Log Files
- VirusTotal

## Key Takeaways

- Windows logs provide valuable evidence for security investigations.
- Event ID 4624 and 4625 help investigate authentication activity.
- User management events can reveal suspicious account modifications.
- Sysmon provides detailed information about process execution and system activity.
- Logon ID helps correlate events associated with a user session.
- Process ID helps connect related Sysmon events.
- PowerShell history can reveal commands executed by users.

## Repository Structure

```text
04-Windows-Logging-for-SOC/
│
├── README.md
│
├── Technical-Notes/
│   ├── windows-event-logging.md
│   ├── important-windows-event-ids.md
│   ├── authentication-log-analysis.md
│   ├── sysmon-investigation.md
│   └── powershell-logging.md
│
└── Investigation-Examples/
    └── windows-log-investigation.md
```

## Completion

**TryHackMe Room:** Windows Logging for SOC

This room strengthened my understanding of Windows security monitoring and gave me a foundation for investigating suspicious activity through event logs.

*Continuously learning, practicing, and building practical SOC Analyst skills.*
