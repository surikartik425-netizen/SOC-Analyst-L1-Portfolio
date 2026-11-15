# SOC L1 Alert Investigation Workflow

## 1. Introduction

Alert investigation is a core responsibility of a SOC Level 1 Analyst.

After selecting and prioritizing an alert, the analyst must investigate the available information to understand what happened, identify potentially suspicious activity, and determine whether the alert represents a genuine security threat.

The investigation process involves initial actions, technical analysis, and final actions.

## 2. Phase 1: Initial Actions

Before beginning an investigation, the analyst should establish ownership of the alert and understand its details.

### Step 1: Assign the Alert

Assign the selected alert to yourself to establish responsibility for the investigation.

### Step 2: Change the Status

Move the alert status from New / Unassigned to In Progress.

This indicates that an analyst has started working on it.

### Step 3: Review Alert Information

Examine the following:

- Alert name
- Alert description
- Alert severity
- Alert creation time
- Affected user
- Hostname
- Source and destination IP addresses
- Relevant process or file information

Understanding these details provides the foundation for the investigation.

## 3. Phase 2: Investigation

This is the main technical analysis stage.

The objective is to determine whether the activity described in the alert is legitimate, suspicious, or malicious.

### Step 1: Identify the Affected Entity

Determine what is potentially under threat.

Examples include:

- User account
- Endpoint or workstation
- Server
- Network
- Cloud environment
- Website

### Step 2: Understand the Detected Activity

Identify what triggered the alert.

Examples:

- Suspicious login
- Malware execution
- Phishing email
- Unauthorized file download
- Unusual network traffic
- Potential data exfiltration

### Step 3: Review Surrounding Events

Analyze related logs and activities that occurred before and after the alert.

Look for:

- Unusual login attempts
- Unexpected process execution
- Suspicious file creation
- Unusual outbound network connections
- Multiple failed authentication attempts
- Other related security alerts

The objective is to understand the context and identify potentially connected activities.

### Step 4: Verify Using Threat Intelligence

Use available threat intelligence resources to investigate suspicious indicators.

Examples of useful resources include:

- VirusTotal – File and URL analysis.
- AbuseIPDB – IP address reputation.
- WHOIS – Domain registration information.
- URLScan.io – Website and URL analysis.

Threat intelligence results should be treated as supporting evidence rather than definitive proof of malicious activity.

### Step 5: Document Findings

Record the important information discovered during the investigation.

Examples:

- Affected hostname
- Username
- Source IP address
- Destination IP address
- File name
- File hash
- Suspicious URL
- Relevant timestamps
- Related log entries

Accurate documentation makes it easier to explain the investigation and support the final verdict.

## 4. Phase 3: Final Actions

After completing the investigation, the analyst must determine the appropriate classification and document the result.

### Step 1: Determine the Verdict

There are two primary classifications.

**True Positive**

Use this classification when investigation confirms that the alert represents genuinely malicious or unauthorized activity.

**False Positive**

Use this classification when investigation establishes that the detected activity was legitimate or harmless.

The verdict must be based on evidence.

### Step 2: Write an Investigation Comment

Prepare a detailed comment explaining:

- What triggered the alert.
- What information was examined.
- What investigation steps were performed.
- What evidence was discovered.
- Why the selected verdict is appropriate.

### Step 3: Escalate When Necessary

If the investigation identifies a genuine threat or activity requiring deeper analysis, escalate it to the SOC L2 team according to the organization's procedures.

SOC L1 analysts perform initial investigation, while L2 analysts handle deeper investigation and remediation.

### Step 4: Update the Alert Status

After completing the required triage actions and documentation, update the alert to Closed / Resolved as appropriate.

## 5. Example Investigation Workflow

Consider an alert named:

**Double-Extension File Creation**

An analyst might follow this workflow:

1. Assign the alert to themselves.
2. Change its status to In Progress.
3. Review the hostname, username, process, file path, and file hash.
4. Examine the suspicious filename and download source.
5. Investigate related endpoint and network activity.
6. Check the file hash and URL using available threat intelligence resources.
7. Document the investigation findings.
8. Determine the appropriate verdict.
9. Escalate if necessary and update the alert according to SOC procedures.

The final verdict cannot be determined from the filename alone. Additional investigation is required.

## 6. Importance of Investigation Documentation

Good investigation documentation should be:

- Accurate and evidence-based.
- Clear and easy to understand.
- Organized in a logical sequence.
- Supported by relevant indicators and observations.
- Free from unsupported assumptions.

A well-written investigation report helps other SOC analysts understand the incident and continue the investigation if required.

## 7. Key Takeaways

- Always establish alert ownership before investigating.
- Review alert properties to understand the detected activity.
- Investigate the affected user, host, and relevant events.
- Use threat intelligence to support analysis.
- Document all important findings.
- Select True Positive or False Positive based on evidence.
- Escalate genuine threats when deeper investigation is required.
- Update the alert status after completing the required actions.

## 8. Practical Learning

**Platform:** TryHackMe

**Room:** SOC L1 Alert Triage

**Learning Outcome:** Learned a structured approach to initial alert handling, investigation, evidence collection, verdict classification, documentation, and escalation.

---

*This document summarizes the alert investigation workflow covered in the TryHackMe SOC L1 Alert Triage room.*
