# Authentication Log Analysis

## 1. Introduction

Authentication logs help SOC analysts investigate successful and failed logins, brute-force attacks, password spraying, and potentially compromised accounts.

The two important Windows Security Event IDs are:

- **4624:** Successful Logon.
- **4625:** Failed Logon.

## 2. Important Fields in Event ID 4624

When analyzing a successful login, review:

- **Logon ID:** Unique identifier for the login session.
- **Logon Type:** Indicates the type of login.
- **Account Name:** User account involved.
- **Source IP Address:** Origin of the login.
- **Workstation Name:** System from which the login originated.

## 3. Detecting RDP Brute Force

1. Open Security logs in Event Viewer.
2. Filter for Event ID `4625`.
3. Review Logon Types `3` and `10`.
4. Look for suspicious activity:

   - Many different usernames being attempted — possible password spraying.
   - Repeated failures against one account — possible brute force.
   - Unexpected workstation names.
   - Unusual source IP addresses.

## 4. Analyzing Successful RDP Logons

1. Filter Security logs for Event ID `4624`.
2. Look for Logon Type `10`.
3. If Network Level Authentication (NLA) is enabled, a Type `3` event may precede the RDP logon.
4. Review the preceding Type `3` event for workstation information.
5. Check for preceding failed logins or suspicious source addresses.
6. Record the Logon ID for further investigation.

## 5. Correlating Authentication Events

A Logon ID can help connect different events from the same session.

For example:

1. Identify a suspicious user-management event.
2. Copy its Subject Logon ID.
3. Search for a corresponding Event ID `4624`.
4. Compare the Logon ID values.
5. Investigate the source IP, account, and logon type.

## SOC Analyst Takeaway

A successful login is not automatically malicious. Analyze the account, source IP, workstation, timestamp, and surrounding events before making a verdict.
