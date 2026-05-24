# BEC KY Investigation: Blue Team Labs Online

## Overview

This project documents my investigation of the BEC KY lab from Blue Team Labs Online. The scenario involved a Business Email Compromise affecting a company pension fund.

The organization observed multiple authorized bank transfers from a pension account to external bank accounts over a 48 hour period. Because the CFO had authority to approve these transactions, the investigation began with Azure audit logs and email evidence.

This lab gave me practical experience analyzing a financial cyber incident involving phishing, account compromise, suspicious cloud activity, inbox rule abuse, and fraudulent transaction activity.

## Scenario Summary

The organization was dealing with a potential financial cyber incident involving its company pension fund. Multiple high value bank transfers were processed from the pension account to external bank accounts, both domestic and international.

The provided evidence included:

* Azure audit logs
* Email exports
* Suspicious financial communication
* Mailbox activity tied to the CFO account

The goal was to determine how the compromise occurred, what attacker activity was visible in the logs, and how the attacker attempted to hide evidence.

## Objective

The objective of this investigation was to:

* Identify the phishing source
* Determine the type of compromise
* Review Azure audit logs for suspicious activity
* Identify attacker source IP addresses
* Analyze mailbox activity
* Identify suspicious inbox folder creation
* Review malicious inbox rule behavior
* Trace the fraudulent bank transfer evidence
* Reconstruct the Business Email Compromise lifecycle

## Key Investigation Data

| Evidence Type | Finding |
|---|---|
| Suspicious sender | sabastian@flanaganspensions.co.uk |
| Attack type | Business Email Compromise |
| Attacker IP 1 | 159.203.17.81 |
| Attacker IP 2 | 95.181.232.30 |
| SWIFT code | FBNINGLA |
| Destination bank | First Bank of Nigeria Ltd |
| Suspicious folder | History |
| Rule keyword | Withdrawal |
| Rule action | DeleteMessage set to True |
| Notable rule time | 2025 07 02T15:48:39Z |

## Skills Demonstrated

* Business Email Compromise investigation
* Phishing analysis
* Azure audit log analysis
* Email artifact review
* Cloud identity investigation
* Suspicious sign in analysis
* Inbox rule analysis
* Threat actor infrastructure review
* Financial fraud investigation
* Evidence correlation
* Timeline reconstruction
* Incident documentation
* Defensive reporting

## Tools and Evidence Used

* Azure audit logs
* Email exports
* Email header review
* Cloud authentication activity
* Mailbox rule events
* IP address review
* SWIFT code lookup
* PowerShell log parsing
* OSINT review
* Timeline analysis

## Investigation Methodology

### 1. Email Review

The investigation started with the provided email exports. The goal was to identify whether a phishing message or suspicious external sender may have initiated the compromise.

The suspicious sender identified was:

```text
sabastian@flanaganspensions.co.uk

This sender appeared to use a lookalike pension related domain. The message theme matched the financial context of the incident and likely served as the initial phishing vector.

2. Compromise Classification

The activity was consistent with Business Email Compromise.

There was no obvious malware or ransomware activity. Instead, the attacker appeared to use valid mailbox access to support fraudulent financial transfers.

The key issue was trust abuse. The attacker used a compromised account and financial context to make the activity appear legitimate.

3. Azure Audit Log Analysis

The Azure audit logs were reviewed to identify suspicious mailbox and account activity.

The investigation focused on:

Mailbox access events
Suspicious source IP addresses
New inbox rule creation
Folder creation
Activity near the financial transfer timeline
Events tied to the affected account

The suspicious IP addresses identified were:

159.203.17.81
95.181.232.30

These IP addresses were tied to suspicious mailbox activity and helped connect the phishing event to unauthorized access.

4. PowerShell Log Parsing

To review the Azure audit logs more efficiently, I used PowerShell style parsing to extract client IP addresses from the audit data field.

Example approach:

Import-Csv .\azure-export-audit-diff |
  ForEach-Object {
    if ($_.AuditData -match '"ClientIP":"([0-9]{1,3}(\.[0-9]{1,3}){3})"') {
        [PSCustomObject]@{
            CreationDate = $_.CreationDate
            Operation    = $_.Operation
            UserId       = $_.UserId
            ClientIP     = $matches[1]
        }
    }
  } | Sort-Object CreationDate | Format-Table -AutoSize

This helped pull key audit fields into a readable format and made it easier to correlate activity by time, operation, user, and source IP.

Example suspicious events:

CreationDate           Operation          ClientIP
2025 07 02T15:42:10Z   MailItemsAccessed  159.203.17.81
2025 07 02T15:48:39Z   New InboxRule      95.181.232.30
5. Attacker Infrastructure Review

The two suspicious IP addresses were not treated as isolated indicators. They were reviewed in the context of:

Mailbox activity
Timing of the fraudulent transfers
New inbox rule creation
Suspicious email evidence
Unusual access behavior

This helped build a clearer picture of how the attacker accessed and manipulated the mailbox.

6. Financial Transfer Review

The compromised email evidence included a SWIFT code tied to the fraudulent transfer activity.

The SWIFT code identified was:

FBNINGLA

A lookup connected this SWIFT code to:

First Bank of Nigeria Ltd

This helped trace the destination of the suspicious transfer activity and supported the conclusion that the incident involved financial fraud.

7. Inbox Folder Analysis

The attacker created or used a suspicious mailbox folder named:

History

This folder was used as part of the attacker concealment activity. The folder helped hide or redirect messages that could have exposed the fraudulent activity.

8. Inbox Rule Analysis

The Azure audit logs showed suspicious inbox rule creation.

The rule searched for the keyword:

Withdrawal

The rule action showed:

DeleteMessage = True

This means the attacker configured the mailbox to delete messages containing the word Withdrawal. This was likely done to suppress bank alerts, transaction confirmations, or warning messages related to the pension fund transfers.

This was one of the strongest pieces of evidence because it showed intentional concealment.

Attack Timeline
Time or Phase	Activity
Initial phishing	Suspicious pension themed email sent from sabastian@flanaganspensions.co.uk
Account compromise	Attacker gained access to the CFO mailbox
Mailbox access	Suspicious access observed from 159.203.17.81
Rule creation	New inbox rule activity observed from 95.181.232.30
Concealment	Folder named History used to hide messages
Rule keyword	Messages containing Withdrawal targeted
Deletion behavior	DeleteMessage set to True
Financial impact	Transfers linked to SWIFT code FBNINGLA and First Bank of Nigeria Ltd
Key Findings

The investigation found that:

The incident was consistent with Business Email Compromise
The likely initial vector was a phishing email
The suspicious sender was sabastian@flanaganspensions.co.uk
The attacker accessed the mailbox from suspicious external IP addresses
The IP addresses 159.203.17.81 and 95.181.232.30 were tied to attacker activity
The attacker created or used the History folder to conceal messages
A malicious inbox rule targeted the word Withdrawal
The inbox rule was configured to delete matching messages
The fraudulent transfer evidence included SWIFT code FBNINGLA
The SWIFT code pointed to First Bank of Nigeria Ltd
The attacker attempted to hide transaction related warnings and alerts
Attack Lifecycle

The incident followed a common Business Email Compromise pattern:

Phishing email delivered to the target
Account credentials or mailbox access obtained
Attacker accessed the mailbox using valid credentials
Attacker reviewed financial communication
Fraudulent transfers were processed
Inbox folder and rule activity was used to hide evidence
Messages containing Withdrawal were deleted
Financial fraud continued until detected
Defensive Lessons Learned

This lab reinforced several important defensive lessons:

Business Email Compromise can cause major financial loss without malware
Cloud audit logs are critical during mailbox compromise investigations
Inbox rule creation should be monitored closely
Suspicious mailbox folder creation can reveal attacker concealment
Finance related keywords in mailbox rules can indicate fraud
Source IP addresses should be correlated with mailbox activity and timestamps
Email evidence and Azure audit logs should be reviewed together
Analysts need to understand both technical evidence and business impact
Recommended Defensive Actions

Based on the investigation, recommended actions would include:

Disable or remove malicious inbox rules
Reset affected user credentials
Revoke active sessions and refresh tokens
Review MFA status
Enforce stronger authentication controls
Review conditional access policies
Investigate suspicious sign in activity
Review recent financial approvals
Alert on suspicious inbox rule creation
Alert on mailbox deletion rules
Alert on forwarding rules
Alert on finance related mailbox rule keywords
Require out of band verification for large fund transfers
Train finance and executive staff on Business Email Compromise indicators
Related Media

Video walkthrough:

https://www.youtube.com/watch?v=pbdiTVopRrQ
What This Project Demonstrates

This project demonstrates my ability to:

Investigate Business Email Compromise activity
Analyze phishing evidence
Review Azure audit logs
Correlate email and cloud activity
Identify suspicious mailbox rules
Trace attacker concealment techniques
Review financial fraud indicators
Extract useful evidence from log data
Build a timeline from multiple sources
Recommend practical defensive actions
Communicate technical findings clearly
Disclosure Notice

This writeup is based on a retired Blue Team Labs Online training environment. It is intended to document the investigation process, skills practiced, and defensive concepts learned.

This page does not include private customer data, employer data, or production system information.
