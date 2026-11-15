# Investigation Report 02: Potential Data Exfiltration

## 1. Executive Summary

A critical alert was triggered after a workstation transferred
5.8 GB of data to an external destination associated with Zoom.

The investigation context identified the traffic as legitimate
Zoom activity on a meeting-room network.

The alert was classified as a False Positive.

## 2. Alert Information

| Field | Details |
|---|---|
| Alert Name | Potential Data Exfiltration |
| Date | March 21, 2025 |
| Time | 13:30 |
| Severity | Critical |
| Status | Closed |
| Verdict | False Positive |
| Assignee | You (L1) |

## 3. Network Information

| Field | Details |
|---|---|
| Source IP | 192.168.45.66 |
| Destination | *.zoom.us |
| Source Network | UK04/MEETINGROOM |
| Data Sent | 5.8 GB |
| Data Received | 5.2 GB |

## 4. Investigation Steps

### Step 1: Alert Review

Reviewed the alert description and identified unusually
high network traffic.

### Step 2: Traffic Analysis

Examined the source IP, destination, and transferred data.

The system recorded 5.8 GB sent and 5.2 GB received.

### Step 3: Destination Analysis

Reviewed the destination domain pattern (*.zoom.us).

The available investigation context associated the
destination with legitimate Zoom communication.

### Step 4: Network Context

Identified the source network as UK04/MEETINGROOM.

The activity was identified as legitimate meeting-related
traffic in the lab context.

### Step 5: Verdict Determination

The available context did not establish unauthorized
data transfer.

The alert was classified as a False Positive.

## 5. Findings

- High-volume network traffic detected.
- Source IP: 192.168.45.66.
- Destination associated with Zoom.
- Source network: UK04/MEETINGROOM.
- Legitimate activity identified in the lab context.
- No confirmed data exfiltration established.

## 6. Response Actions

- Reviewed the available network information.
- Evaluated the destination and business context.
- Documented the legitimate activity.
- Classified the alert as a False Positive.
- Closed the alert.

## 7. Final Assessment

**Verdict:** FALSE POSITIVE

**Severity:** Critical

**Status:** Closed

The alert was triggered by a high-volume traffic detection
rule, but the available investigation context identified
the activity as legitimate Zoom traffic.

## 8. Analyst Notes

High network traffic alone is insufficient to establish
data exfiltration.

In a real SOC environment, the analyst should additionally
validate application logs, meeting schedules, proxy records,
firewall events, and business authorization before closing
a critical alert.
