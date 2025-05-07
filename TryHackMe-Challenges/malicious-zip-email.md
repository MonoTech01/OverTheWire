
## Ticket ID: 1001

**Description:**  A suspicious attachment was found in an inbound email. Further investigation was required to determine if it was malicious.

### Email Details

- **Datasource:** Emails  
- **Timestamp:** 2025-05-01 01:31:40.773  
- **Direction:** Inbound  
- **Sender:** john@hatmakereurope.xyz  
- **Recipient:** michael.ascot@tryhatme.com  
- **Subject:** Important: Pending Invioce!  
- **Attachment:** ImportantInvoice-Febrary.zip  
- **Content:** Redacted due to privacy and company security policies

---

### Ticket Performance

- **Analyst:** Mono  
- **Status:** Closed  
- **Priority:** High  
- **Category:** Email Threat – Suspicious Attachment  

### Summary

An inbound email was flagged due to a suspicious `.zip` attachment and multiple phishing indicators. The subject line and attachment name both contained typographical errors ("Invioce" and "Febrary"), suggesting an attempt to bypass email filters. The email originated from a `.xyz` domain, which is often associated with low-reputation or malicious activity. No interaction with the attachment occurred at the time of detection.

### Observations

- Spelling errors in both subject and attachment suggest phishing attempt.
- `.zip` attachment is a common delivery method for malware.
- Sender’s `.xyz` domain is frequently used in spam or malicious campaigns.
- Urgent tone in the subject line designed to pressure user action.

### Report

On May 1, 2025, at 01:31:40, an inbound email was received by michael.ascot@tryhatme.com from john@hatmakereurope.xyz with a suspicious attachment named "ImportantInvoice-Febrary.zip." The email used urgency and typographical errors in both the subject and filename to mimic an invoice request and bypass filters. While the email content was redacted due to privacy policy, the observed indicators strongly suggested malicious intent. The email was quarantined, and the attachment was sent for further analysis.

### Actions Taken

- Quarantined the suspicious email  
- Notified the recipient to avoid interaction  
- Submitted the attachment to a sandbox for malware analysis  
- Searched the environment for similar indicators  
- Escalated to Tier 2 SOC for deeper investigation  
