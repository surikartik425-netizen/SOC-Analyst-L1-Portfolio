# Important Windows Event IDs

## 1. Security Log — Authentication

| Event ID | Description |
|---|---|
| 4624 | Successful Logon |
| 4625 | Failed Logon |

### Important Logon Types

- **Type 3:** Network Logon.
- **Type 10:** Remote Interactive Logon (commonly RDP).

## 2. Security Log — User Management

| Event ID | Description |
|---|---|
| 4720 | User Account Created |
| 4722 | User Account Enabled |
| 4738 | User Account Changed |
| 4725 | User Account Disabled |
| 4726 | User Account Deleted |
| 4723 | User Password Changed |
| 4724 | User Password Reset |
| 4732 | Member Added to Security Group |
| 4733 | Member Removed from Security Group |

## 3. Process Creation

| Event ID | Source | Description |
|---|---|---|
| 4688 | Windows Security | Process Creation |
| 1 | Sysmon | Process Creation |

## 4. Additional Sysmon Events

| Event ID | Description |
|---|---|
| 3 | Network Connection |
| 11 | File Creation |
| 13 | Registry Value Set |
| 22 | DNS Query |

## Important Correlation Fields

- **Logon ID:** Helps correlate events associated with the same user session.
- **Process ID:** Helps correlate Sysmon events associated with a process.

## SOC Analyst Takeaway

These Event IDs are useful starting points for investigating authentication activity, account manipulation, process execution, file changes, and network connections.
