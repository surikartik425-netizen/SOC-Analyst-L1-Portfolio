# PowerShell Logging

## 1. Introduction

PowerShell is a powerful Windows administration tool that can also be abused by attackers.

Attackers may use PowerShell for:

- System discovery.
- Reading sensitive files.
- Downloading malware.
- Data exfiltration.
- Executing malicious commands.

## 2. Why Process Monitoring Is Not Enough

Sysmon Event ID `1` can show that `powershell.exe` was launched, but it does not automatically record every command executed inside that PowerShell session.

Therefore, SOC analysts need additional ways to review PowerShell activity.

## 3. PowerShell History File

The room introduces the PowerShell history file:

`C:\Users\<USER>\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadline\ConsoleHost_history.txt`

This is a plain-text file that records commands entered into a PowerShell window.

Each user has their own history file.

## 4. What Can Be Investigated?

PowerShell history can help identify:

- Commands executed by a user.
- The order in which commands were entered.
- Commands used for system discovery.
- Commands used to access files.
- Commands used to download files.

## 5. Limitations

- It does not record command output.
- It does not show the contents of a script executed using a command such as `powershell .\script.ps1`.
- The history file can be manually deleted.

## 6. Investigation Workflow

1. Identify the Windows user account.
2. Navigate to the user's PowerShell history directory.
3. Open `ConsoleHost_history.txt`.
4. Review the commands in order.
5. Look for suspicious commands related to discovery, file access, or downloads.
6. Check the file Properties when investigating its creation or modification details.
7. Review other local users' history files if necessary.

## SOC Analyst Takeaway

PowerShell history can provide useful evidence during an investigation, but it is not a complete record of PowerShell activity. Correlate it with other available Windows and Sysmon logs.
