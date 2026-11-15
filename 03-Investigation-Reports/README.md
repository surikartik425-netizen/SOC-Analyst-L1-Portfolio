# Investigation Report 01: Double-Extension File Creation

## 1. Executive Summary

A high-severity alert was generated after a suspicious
double-extension executable was downloaded to a workstation.

Investigation identified a suspicious external URL and a
file with multiple VirusTotal detections.

The alert was classified as a True Positive.

## 2. Alert Information

| Field | Details |
|---|---|
| Alert Name | Double-Extension File Creation |
| Date | March 21, 2025 |
| Time | 13:58 |
| Severity | High |
| Status | Closed |
| Verdict | True Positive |
| Assignee | You (L1) |

## 3. Affected System

| Field | Details |
|---|---|
| Hostname | LPT-HR-009 |
| Username | S.Conway |
| Process | chrome.exe |
| File | cats2025.mp4.exe |
| File Path | C:\Users\S.Conway\Downloads\ |
| Source URL | freecatvideoshd.monster/cats2025.mp4.exe |
| MD5 | 14d8486f3f63875ef93cfd240c5dc10b |

## 4. Investigation Steps

### Step 1: Alert Review

Reviewed the alert description and identified a suspicious
double-extension executable file.

### Step 2: File Analysis

Examined the filename cats2025.mp4.exe.

The .exe extension indicated an executable file rather
than a standard MP4 video.

### Step 3: Source Analysis

Reviewed the source URL and identified an untrusted
external website.

### Step 4: Hash Verification

Checked the MD5 hash using VirusTotal.

The file received multiple security detections,
increasing confidence that it was malicious.

### Step 5: Verdict Determination

Correlated the suspicious extension, download source,
and VirusTotal findings.

The evidence supported a True Positive classification.

## 5. Findings

- Suspicious executable downloaded by the user.
- Double-extension technique identified.
- Untrusted source URL identified.
- Multiple VirusTotal detections observed.
- Malicious file download confirmed in the lab context.

## 6. Response Actions

- Recommended quarantining the suspicious file.
- Recommended scanning the affected workstation.
- Recommended checking whether the executable was launched.
- Recommended reviewing endpoint logs.
- Documented the findings.

## 7. Final Assessment

**Verdict:** TRUE POSITIVE

**Severity:** High

**Status:** Closed

The alert was correctly classified as a True Positive.
Containment and further endpoint verification were recommended.

## 8. Analyst Notes

The available lab evidence confirmed a suspicious file download.
It did not independently establish whether the executable
was successfully executed or whether the workstation was
fully compromised.

Further endpoint investigation would be necessary to
determine the extent of any compromise.
