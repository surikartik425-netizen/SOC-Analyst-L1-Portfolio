# Sysmon Investigation

## 1. What Is Sysmon?

Sysmon (System Monitor) is a Microsoft Sysinternals tool that provides detailed information about activity on Windows systems.

It helps SOC analysts monitor:

- Process creation.
- Network connections.
- File creation.
- Registry changes.
- DNS queries.

Sysmon logs can be found in Event Viewer under:

`Applications and Services → Microsoft → Windows → Sysmon → Operational`

## 2. Sysmon Event ID 1 — Process Creation

Event ID `1` records process creation.

Important fields include:

### Process Information
- Process ID (PID)
- Image path
- Command line

### Parent Information
- Parent Process ID
- Parent image
- Parent command line

### Binary Information
- Process hash
- Signature
- PE metadata

### User Context
- User account
- Logon ID

## 3. Process Investigation Workflow

1. Open Sysmon Operational logs.
2. Filter for Event ID `1`.
3. Review process name, image path, command line, and hash.
4. Examine the parent process.
5. Check whether the parent-child relationship is expected.
6. If necessary, trace the process tree using Process ID and Parent Process ID.
7. Correlate related events using Logon ID.

### Suspicious Indicators

- Executables running from `C:\Temp` or `C:\Users\Public`.
- Randomly generated process names.
- Hashes identified as malicious by threat intelligence.
- Unexpected parent-child process relationships.

## 4. Additional Sysmon Event IDs

| Event ID | Description |
|---|---|
| 3 | Network Connection |
| 11 | File Creation |
| 13 | Registry Value Set |
| 22 | DNS Query |

## 5. Correlating Sysmon Events

1. Identify the Process ID from Event ID `1`.
2. Search for other Sysmon events with the same Process ID.
3. Review network connections, file creation, registry changes, and DNS queries.
4. Return to Event ID `1` to understand the process context.

### Suspicious Activity to Investigate

- Connections to unexpected external IP addresses.
- Connections on unusual ports, such as `4444`.
- DNS queries to suspicious domains.
- Executables or scripts created in unusual directories.
- Unexpected registry changes.

## SOC Analyst Takeaway

Sysmon provides detailed visibility into endpoint activity. Correlating events using Process ID helps reconstruct suspicious process activity and understand a potential attack chain.
