# Case Study 02: Potential Data Exfiltration

## 1. Overview

A critical security alert was generated after a workstation
transferred more than 5 GB of data to an external destination.

The monitoring rule identified unusually high data transfer
activity, which could indicate potential data exfiltration.

However, the investigation context indicated that the traffic
was associated with legitimate Zoom activity.

## 2. Incident Details

- Alert Name: Potential Data Exfiltration
- Date: March 21, 2025
- Time: 13:30
- Severity: Critical
- Source IP: 192.168.45.66
- Destination: *.zoom.us
- Source Network: UK04/MEETINGROOM
- Data Sent: 5.8 GB
- Data Received: 5.2 GB
- Final Verdict: False Positive

## 3. What Happened?

The security monitoring system detected a large volume of
network traffic between a device and a destination associated
with Zoom.

The detection rule triggered because more than 5 GB of data
was transferred from a single device to a single destination
within a day.

High-volume outbound traffic can sometimes indicate
unauthorized data transfers.

Therefore, the alert required investigation.

## 4. Investigation and Analysis

The following information was available:

1. The source IP address was 192.168.45.66.
2. The destination was *.zoom.us.
3. The source network was UK04/MEETINGROOM.
4. Approximately 5.8 GB of data was sent.
5. Approximately 5.2 GB of data was received.

The investigation context identified the traffic as legitimate
Zoom activity.

The traffic pattern was consistent with high-bandwidth
meeting-related communication rather than confirmed
unauthorized data transfer.

## 5. Potential Security Risks

If the traffic had been unauthorized, it could have indicated:

- Unauthorized transfer of confidential information.
- Data leakage to an external destination.
- Compromised user accounts.
- Misuse of legitimate cloud services.

However, the available investigation context did not
establish any of these activities.

## 6. Why Was It a False Positive?

The detection rule identified high-volume network traffic,
but high data transfer alone does not prove data exfiltration.

The available context associated the traffic with legitimate
Zoom activity on the meeting-room network.

No confirmed evidence of unauthorized data transfer was
recorded in the lab investigation.

## 7. Recommended Response

- Verify the destination and application.
- Correlate network activity with meeting schedules.
- Review firewall, proxy, and network logs.
- Confirm whether the traffic was authorized.
- Document the legitimate business activity.
- Tune detection thresholds if repeated legitimate activity
  causes unnecessary alerts.

## 8. Final Verdict

FALSE POSITIVE

The alert was classified as a False Positive because the
available investigation context identified the high-volume
traffic as legitimate Zoom activity.

The alert was closed after documenting the findings.

## 9. Key Learning Outcomes

- Understand data exfiltration detection.
- Analyze unusual network traffic volumes.
- Understand the importance of destination analysis.
- Avoid treating every high-volume transfer as malicious.
- Learn how legitimate business applications can trigger alerts.

## 10. SOC Analyst L1 Takeaway

A high-volume data transfer is a reason to investigate,
not automatic proof of data exfiltration.

Always correlate network traffic with application activity,
business context, and supporting security logs before
assigning a final verdict.
