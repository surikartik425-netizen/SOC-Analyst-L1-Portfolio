# Investigation Report 03: Download from GitHub Repository

## 1. Executive Summary

A low-severity alert was triggered after a user accessed
a GitHub repository.

The investigation context identified the activity as
legitimate development-related access from the
VPN/DEVELOPERS network.

The alert was classified as a False Positive.

## 2. Alert Information

| Field | Details |
|---|---|
| Alert Name | Download from GitHub Repository |
| Date | March 21, 2025 |
| Time | 13:02 |
| Severity | Low |
| Status | Closed |
| Verdict | False Positive |
| Assignee | You (L1) |

## 3. Event Information

| Field | Details |
|---|---|
| Accessed URL | https://github.com/facebook/react |
| Source User | G.Chandler |
| Source Host | LPT-IT-063 |
| Source Network | VPN/DEVELOPERS |

## 4. Investigation Steps

### Step 1: Alert Review

Reviewed the alert and identified access to a GitHub
repository.

### Step 2: URL Analysis

Examined the accessed URL:

https://github.com/facebook/react

The repository was associated with the React project.

### Step 3: User Analysis

Identified the source user as G.Chandler.

### Step 4: Host and Network Analysis

Identified the source host as LPT-IT-063 and the
network as VPN/DEVELOPERS.

### Step 5: Verdict Determination

The available lab context identified the activity
as legitimate development-related access.

No malicious activity was established in the
provided investigation findings.

The alert was classified as a False Positive.

## 5. Findings

- GitHub repository access detected.
- Repository: facebook/react.
- Source user: G.Chandler.
- Source host: LPT-IT-063.
- Source network: VPN/DEVELOPERS.
- Legitimate development activity identified.

## 6. Response Actions

- Reviewed the accessed repository.
- Examined available user and host information.
- Evaluated the network context.
- Documented the investigation findings.
- Classified the alert as a False Positive.
- Closed the alert.

## 7. Final Assessment

**Verdict:** FALSE POSITIVE

**Severity:** Low

**Status:** Closed

The available investigation context indicated legitimate
development-related GitHub access.

No further action was required according to the lab outcome.

## 8. Analyst Notes

GitHub is a legitimate software development platform,
but repositories can also contain malicious code.

SOC analysts should evaluate the repository, downloaded
files, user role, endpoint activity, and business context
before determining whether the activity is malicious.
