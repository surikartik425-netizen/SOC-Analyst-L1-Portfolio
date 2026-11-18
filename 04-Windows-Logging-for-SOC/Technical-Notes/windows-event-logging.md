# Windows Event Logging

## 1. What Is Logging?

Whenever an action occurs in Windows, such as starting a program, creating a file, or logging in, the operating system can record that activity as an event.

Logs help SOC analysts with:

- **Incident Response:** Understand when and how an attack occurred.
- **Threat Hunting:** Search for signs of malicious activity.
- **Alerting and Triage:** Provide data for security alerts and detection rules.

## 2. Windows EVTX Files

Windows event logs are stored in EVTX format in:

`C:\Windows\System32\winevt\Logs`

Each EVTX file corresponds to a specific log category.

- **Application Logs:** Events recorded by applications such as IIS or MS SQL.
- **Security Logs:** Events such as logon attempts, process activity, and user management.

## 3. Reading Logs with Event Viewer

Event Viewer is a built-in Windows tool used to view and manage event logs.

To open it:

1. Press `Win + R`.
2. Type `eventvwr`.
3. Press Enter.

### Main Components

1. **Log Sources:** Available log categories.
2. **Log List:** Individual events with timestamps and Event IDs.
3. **Log Details:** Event information in readable or XML format.
4. **Filters:** Use Filter Current Log and Find to locate specific events.

## 4. Important Points

- Every event has an Event ID.
- Event Viewer displays system time, not necessarily UTC.
- Not all events are enabled or recorded by default.
- Analysts should understand the event details, not just memorize Event IDs.

## SOC Analyst Takeaway

Windows logs provide valuable evidence during investigations. Always review the event details and correlate related events before reaching a conclusion.
