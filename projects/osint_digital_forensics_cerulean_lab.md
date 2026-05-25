---
layout: project
title: OSINT and Digital Forensics Cerulean Lab
---
# OSINT and Digital Forensics Lab: Cerulean Investigation

## Overview

This project documents my investigation of the Cerulean digital forensics lab. The scenario involved suspicious RDP connections to the Production Department at Cerulean Inc., with special focus on Jane’s workstation.

The investigation focused on analyzing triage artifacts, reviewing browser history, identifying suspicious RDP activity, investigating possible data exfiltration, reviewing cloud storage usage, and correlating forensic evidence across multiple tools.

## Video Walkthrough

[Watch my OSINT and Digital Forensics Lab walkthrough on YouTube](https://www.youtube.com/watch?v=aatlPjqz13M)

## Scenario Summary

Cerulean Inc. is a manufacturer of industrial control systems. The SIEM generated alerts for suspicious RDP connections to the Production Department, especially Jane’s PC. Jane was the head of the department.

The activity was later determined to be malicious. The investigation required reviewing triage artifacts from Jane’s computer and investigating whether the RDP activity was connected to data exfiltration.

The investigation focused on:

* Suspicious RDP access
* Browser history review
* Cloud storage access
* Slack usage
* Windows user account review
* Windows Defender logs
* Possible Project Venus data leakage
* OSINT and forensic timeline correlation

## Objective

The objective of this investigation was to:

* Analyze triage artifacts from Jane’s workstation
* Identify when Jane received the malicious email
* Review browser history related to phishing activity
* Investigate suspicious RDP connections
* Identify the origin IP address for RDP access
* Determine whether cloud storage was used for exfiltration
* Identify suspicious Slack usage
* Review Jane’s assigned role and permissions
* Analyze Windows Defender logs for leaked Project Venus documents
* Build a timeline of attacker activity

## Key Investigation Data

| Evidence Type | Finding |
|---|---|
| Organization | Cerulean Inc. |
| Affected user | Jane |
| Affected department | Production Department |
| Main alert source | SIEM |
| Suspicious access type | RDP |
| Origin IP address | `104[.]203[.]174[.]169` |
| Initial RDP time | `11/5/2024 8:58:41 UTC` |
| Storage service with most traffic | Google Drive |
| Insider Threat Matrix ID | `IF001.001` |
| Jane’s assigned role | MSFT Admin (Database Specialist) |
| Suspicious software | Slack |
| Slack install time | `2024-11-05 20:09:51 UTC` |
| Unofficial communication URL | `https://ceruleaninc.slack.com/messages` |
| Project involved | Project Venus |
| Malicious email time | Add exact timestamp from your lab notes |
| Leaked documents | Add four document names from Windows Defender logs |

## Skills Demonstrated

* Digital forensics
* OSINT investigation
* Browser history analysis
* RDP activity review
* Timeline reconstruction
* Windows artifact analysis
* Registry analysis
* Cloud storage investigation
* Insider threat analysis
* Exfiltration analysis
* Windows Defender log review
* Communication platform investigation
* Forensic reporting

## Tools and Evidence Used

* Hindsight
* Registry Explorer
* Magnet AXIOM
* Timeline Explorer
* Event Log Explorer
* Windows Defender logs
* Chrome History database
* Browser history artifacts
* RDP artifacts
* Slack artifacts
* OSINT research
* Insider Threat Matrix

## Investigation Methodology

### 1. Browser History Review

The investigation began by reviewing browser history artifacts to identify when Jane received or accessed a malicious email from an attacker pretending to be IT Support.

The email theme identified was:

```text
IT Support: Remote Check
```

The browser history review helped establish the early part of the incident timeline.

Tools used during this phase included:

* Magnet AXIOM
* Hindsight
* Timeline Explorer
* Chrome History database

The exact malicious email timestamp should be added from the lab evidence:

```text
Add exact malicious email timestamp here
```

### 2. Cloud Storage Activity Review

After reviewing the malicious email timeline, the next step was to identify activity that occurred shortly after the suspicious RDP session.

Browser history showed access to Google Drive.

The storage service with the most traffic was:

```text
Google Drive
```

This was important because the scenario suggested possible data exfiltration through RDP. Google Drive activity shortly after suspicious access created a strong lead for potential data movement.

### 3. Insider Threat Matrix Mapping

The suspected exfiltration behavior was mapped to the Insider Threat Matrix.

The relevant technique ID was:

```text
IF001.001
```

This mapping helped classify the behavior as file based exfiltration activity using an external storage resource.

### 4. User Role Review

Jane’s account was reviewed to determine whether she had excessive privileges.

The assigned role identified was:

```text
MSFT Admin (Database Specialist)
```

This mattered because Jane’s account had administrative rights, which increased the potential impact of compromise. If an attacker gained access through her account or workstation, those privileges could allow broader access to sensitive resources.

### 5. Slack Installation Review

The investigation found evidence that Slack was downloaded before the suspicious RDP session.

The install or usage timeline was reconstructed by reviewing browser and timeline artifacts.

Slack install time:

```text
2024-11-05 20:09:51 UTC
```

The sequence included:

* Google searches for Slack download
* Access to Slack download pages
* `SlackSetup.exe` appearing in Chrome Downloads
* A YouTube video related to installing Slack
* Successful Slack login activity

This was suspicious because the organization primarily used Microsoft Teams for communication.

### 6. Slack Communication Review

The investigation found enough evidence that Slack was used on Jane’s machine.

The unofficial Slack URL identified was:

```text
https://ceruleaninc.slack.com/messages
```

This was important because unofficial communication channels can create visibility gaps for security teams and may be used to coordinate suspicious activity.

### 7. RDP Connection Review

RDP activity was reviewed around the timeline of the malicious email and suspicious workstation activity.

The initial RDP connection was identified as:

```text
11/5/2024 8:58:41 UTC
```

Origin IP address:

```text
104[.]203[.]174[.]169
```

This helped establish when the suspicious remote access began and which external IP address was involved.

### 8. Windows Defender Log Review

The investigation also focused on Project Venus data leakage.

The hint pointed toward Windows Defender logs, including:

* `MPDetection`
* `MPDeviceControl`
* `MpLog.log`

Filtering for the keyword `venus` in `MpLog.log` revealed four Project Venus related documents.

The four leaked documents should be added here after confirming the final names from your lab output:

```text
Doc1, Doc2, Doc3, Doc4
```

## Attack Timeline

| Phase | Activity |
|---|---|
| Phishing activity | Jane received or accessed malicious IT Support themed email |
| Suspicious access | RDP connection observed from `104[.]203[.]174[.]169` |
| Privileged user concern | Jane’s account had MSFT Admin rights |
| Storage access | Google Drive showed the most storage related traffic |
| Communication concern | Slack was downloaded and used despite Teams being the main communication platform |
| Exfiltration concern | Project Venus document activity appeared in Windows Defender logs |
| Evidence correlation | Browser, RDP, Slack, and Defender artifacts were reviewed together |

## Key Findings

The investigation found that:

* Jane’s workstation was tied to suspicious RDP activity
* The origin IP address was `104[.]203[.]174[.]169`
* The initial RDP timestamp was `11/5/2024 8:58:41 UTC`
* Jane’s account had the role `MSFT Admin (Database Specialist)`
* Google Drive had the most traffic among the reviewed storage resources
* The suspected exfiltration activity mapped to `IF001.001`
* Slack was downloaded and used on Jane’s machine
* The unofficial Slack URL was `https://ceruleaninc.slack.com/messages`
* Windows Defender logs contained evidence related to Project Venus documents
* Browser history, timeline artifacts, and Defender logs were critical to the investigation

## Defensive Lessons Learned

This lab reinforced several important defensive lessons:

* RDP activity should be monitored closely on sensitive workstations
* Privileged user accounts increase the impact of compromise
* Browser history can provide strong timeline evidence
* Cloud storage access after suspicious remote login can indicate exfiltration
* Unauthorized communication tools can create security visibility gaps
* Windows Defender logs can contain important evidence of sensitive file activity
* Timeline correlation is critical during digital forensic investigations
* OSINT and forensic artifacts can support each other during incident analysis

## Recommended Defensive Actions

Based on this investigation, recommended actions would include:

* Restrict RDP access to approved sources
* Enforce MFA for remote access
* Review privileged account assignments
* Remove unnecessary administrative rights from user accounts
* Investigate access from `104[.]203[.]174[.]169`
* Review Google Drive activity for suspicious uploads or downloads
* Review Slack usage and block unapproved workspaces if needed
* Monitor for unauthorized collaboration tools
* Review Windows Defender logs for sensitive file activity
* Create alerts for unusual cloud storage access after RDP login
* Conduct user awareness training for fake IT Support messages
* Preserve browser, registry, and event artifacts during future investigations

## What This Project Demonstrates

This project demonstrates my ability to:

* Analyze digital forensic triage artifacts
* Use Hindsight to review browser history
* Use Timeline Explorer to reconstruct activity
* Use Magnet AXIOM for forensic review
* Investigate suspicious RDP activity
* Identify possible cloud based exfiltration
* Review unauthorized communication platform usage
* Analyze Windows Defender logs for sensitive file activity
* Map activity to insider threat techniques
* Build a clear forensic timeline
* Translate forensic evidence into defensive recommendations

## Disclosure Notice

This writeup is based on an authorized Blue Team Labs Online training environment. It is intended to document the investigation process, lab indicators, and defensive concepts learned.

This page does not include private customer data, employer data, production system information, or unauthorized activity.
