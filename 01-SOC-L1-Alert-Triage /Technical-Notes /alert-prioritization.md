# SOC Alert Prioritization

## 1. Introduction

Alert prioritization is the process of determining which security alerts should be investigated first.

SOC teams may receive hundreds of alerts every day. Since analysts cannot investigate every alert simultaneously, prioritization helps ensure that potentially serious security incidents receive attention first.

An effective prioritization process helps reduce investigation delays and ensures that important threats are not overlooked.

## 2. Why Is Alert Prioritization Important?

Alert prioritization is important because:

- SOC teams handle large volumes of security alerts.
- Critical threats require immediate investigation.
- Delayed investigations may increase the impact of a security incident.
- Analysts need to manage their workload efficiently.
- Proper prioritization helps reduce the possibility of missing genuine threats.

## 3. Alert Prioritization Process

The TryHackMe SOC L1 Alert Triage room introduces a simple approach involving three main steps.

### Step 1: Filter the Alerts

Before investigating an alert, check its current status.

- Avoid alerts already assigned to other analysts.
- Avoid alerts that are already being investigated.
- Focus on new, unassigned, and unresolved alerts.

This prevents multiple analysts from unnecessarily investigating the same alert.

### Step 2: Sort by Severity

Prioritize alerts according to their severity.

The general priority order is:

1. Critical
2. High
3. Medium
4. Low / Informational

Critical alerts should generally receive attention before lower-severity alerts because they may indicate serious security threats.

**Example:**

| Alert | Severity | Priority |
|---|---|---|
| Potential Data Exfiltration | Critical | 1 |
| Double-Extension File Creation | High | 2 |
| Unusual Login Location | Medium | 3 |
| Informational Event | Low | 4 |

### Step 3: Sort by Alert Time

When comparing alerts with the same severity, prioritize the older alert before the newer one.

The reason is that an older unresolved security incident may have been active for a longer period and could already be causing damage.

**Example:**

| Alert | Severity | Time |
|---|---|---|
| Suspicious Login | High | 10:00 AM |
| Malware Detection | High | 10:30 AM |

If both alerts are new and unassigned, the older Suspicious Login alert should generally be investigated first.

## 4. Practical Prioritization Example

Consider the following alerts in a SOC dashboard:

| Alert Name | Severity | Status | Verdict |
|---|---|---|---|
| Double-Extension File Creation | High | Awaiting Action | None |
| Potential Data Exfiltration | Critical | Awaiting Action | None |
| Download from GitHub Repository | Low | Awaiting Action | None |
| Unusual VPN Login Location | Medium | Closed | False Positive |
| Bruteforce Attack from External | Medium | Closed | True Positive |

### Analysis

The Potential Data Exfiltration alert should be selected first because:

- It has Critical severity.
- Its status indicates that it is awaiting action.
- It has not yet been assigned.
- It requires investigation to determine whether data was transferred to an untrusted destination.

Previously closed alerts should not be selected as new investigation tasks.

## 5. Important Considerations

Severity should not be the only factor in prioritization.

Analysts should also consider:

- Whether the alert is already being investigated.
- Whether the affected system is business-critical.
- Whether sensitive information is involved.
- Whether the activity is ongoing.
- Whether multiple alerts are connected to the same incident.

Actual SOC environments may use additional risk-based prioritization rules.

## 6. Key Takeaways

- Filter alerts before selecting an investigation.
- Prioritize Critical alerts over High, Medium, and Low alerts.
- When severity is equal, investigate older unresolved alerts first.
- Avoid duplicating work already assigned to another analyst.
- Consider the potential impact and context of the activity.

## 7. Practical Learning

**Platform:** TryHackMe

**Room:** SOC L1 Alert Triage

**Learning Outcome:** Learned how to filter, prioritize, and select security alerts using severity, alert status, and alert creation time.

---

*These notes document the alert prioritization methodology covered in the TryHackMe SOC L1 Alert Triage room.*
