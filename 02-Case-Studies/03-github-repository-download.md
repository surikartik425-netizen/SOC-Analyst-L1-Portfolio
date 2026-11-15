# Case Study 03: Download from GitHub Repository

## 1. Overview

A low-severity security alert was generated after a user
accessed a GitHub repository.

The detection rule monitored GitHub downloads because
repositories can contain malicious scripts, exploits,
and other potentially unsafe files.

However, the investigation context indicated that the
access was legitimate development activity.

## 2. Incident Details

- Alert Name: Download from GitHub Repository
- Date: March 21, 2025
- Time: 13:02
- Severity: Low
- Accessed URL: https://github.com/facebook/react
- Source User: G.Chandler
- Source Host: LPT-IT-063
- Source Network: VPN/DEVELOPERS
- Final Verdict: False Positive

## 3. What Happened?

The monitoring system generated an alert after detecting
access to a GitHub repository.

GitHub is widely used for software development and
collaboration. However, malicious scripts and exploits
can also be distributed through code repositories.

Therefore, the activity required verification.

## 4. Investigation and Analysis

The investigation identified the following:

1. The accessed repository was facebook/react.
2. The source user was G.Chandler.
3. The source host was LPT-IT-063.
4. The source network was VPN/DEVELOPERS.
5. The activity was associated with a development environment.

The available lab context indicated that the user was
accessing GitHub for legitimate development purposes.

No malicious activity was established in the investigation.

## 5. Potential Security Risks

Accessing untrusted code repositories can introduce risks such as:

- Downloading malicious scripts.
- Executing vulnerable or unsafe code.
- Installing compromised dependencies.
- Introducing supply-chain security threats.

However, these risks were not confirmed in this incident.

## 6. Why Was It a False Positive?

The detection rule flagged GitHub access because the
platform can host potentially malicious content.

However, the investigation context identified the access
as legitimate activity from the development VPN.

The alert therefore represented legitimate activity
rather than a confirmed security incident.

## 7. Recommended Response

- Verify the repository being accessed.
- Confirm the user's role and business purpose.
- Review browser and network logs if necessary.
- Check whether any files were downloaded or executed.
- Follow organizational policies for third-party code.
- Document the investigation findings.

## 8. Final Verdict

FALSE POSITIVE

The alert was classified as a False Positive because
the available investigation context identified the
GitHub access as legitimate development activity.

No further action was required according to the
lab investigation outcome.

## 9. Key Learning Outcomes

- Understand GitHub-related security alerts.
- Recognize software supply-chain risks.
- Analyze user, host, and network context.
- Understand legitimate developer activity.
- Avoid unnecessary escalation of benign alerts.

## 10. SOC Analyst L1 Takeaway

A trusted platform does not guarantee that every file
or repository is safe.

Likewise, accessing a platform such as GitHub does not
automatically indicate malicious activity.

Always investigate the repository, user, host, and
business context before reaching a verdict.
