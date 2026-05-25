---
layout: project
title: Haunted Company Threat Intelligence Lab
---
# OSINT Threat Intelligence Lab: Haunted Company Investigation

## Overview

This project documents my OSINT and threat intelligence investigation of the Haunted Company lab. The scenario involved a credit reporting agency preparing for an upcoming Initial Public Offering when one of its websites was defaced and its Tokyo server came under attack.

The investigation focused on decoding intelligence artifacts, reviewing external and internal threat intelligence, analyzing adversary reports, extracting indicators of compromise, identifying attack vectors, and correlating activity to likely threat actor behavior.

## Video Walkthrough

[Watch my OSINT Threat Intelligence Lab walkthrough on YouTube](https://www.youtube.com/watch?v=O1pEh1nN0fg)

## Scenario Summary

Haunted Company Inc. is a long established credit reporting agency operating in major financial hubs such as New York, London, and Tokyo. As the company prepared to go public, one of its websites was defaced. Shortly after, the Tokyo server came under attack.

Because the timing of the incident could damage the company’s reputation before its IPO, management needed threat intelligence analysts to identify the likely adversary, understand the breach mechanism, and develop detection logic before the public offering.

The available intelligence sources included:

* New York external business commonality reporting
* London internal adversary analysis
* Tokyo cyber activity attribution
* Malware and IOC artifacts from the compromised server

## Objective

The objective of this investigation was to:

* Decode provided intelligence artifacts
* Review threat intelligence from multiple regions
* Analyze historical breach reporting
* Identify relevant attacker tactics and vulnerabilities
* Review adversary analysis for finance sector targeting
* Analyze malicious documents and web server artifacts
* Extract indicators of compromise
* Identify likely attack vectors
* Attribute activity to relevant threat actor behavior
* Support detection creation before the IPO

## Key Investigation Data

| Evidence Type | Finding |
|---|---|
| Lab focus | OSINT and threat intelligence |
| Target organization | Haunted Company Inc. |
| Industry | Credit reporting and finance |
| Business event | Upcoming IPO |
| Incident type | Website defacement and Tokyo server compromise |
| External intel source | New York business commonality report |
| Internal intel source | London adversary analysis |
| Cyber activity source | Tokyo malware and IOC analysis |
| Main tools used | CyberChef, ExifTool, OfficeMalScanner |
| Decoding method | Base64 |
| Historical breach company | GenX Finance |
| Historical breach country | US |
| Historical breach business model | Credit Reporting Agency |
| Weakness exploited | Application vulnerability |
| Historical exploited application | Apache Struts |
| Historical CVE | CVE 2017 5638 |
| Affected environment | ACIS |
| Mean Time to Detect | 76 days |
| Code flaws identified | SQL injection, Insecure Direct Object Reference |
| Inserted file type | JSP |
| Attack origin indicator | China |
| Recommended security control | Network Segmentation |
| Threat group analyzed | FIN7 |
| Additional group analyzed | APT27 |
| Related actor alias | Threat Group 3390 |
| Malware or tool family | China Chopper |
| Later RCE CVE identified | CVE 2023 50164 |

## Skills Demonstrated

* OSINT investigation
* Threat intelligence analysis
* CyberChef decoding
* Base64 decoding
* HTML source review
* Developer tools review
* IOC extraction
* ExifTool metadata analysis
* OfficeMalScanner usage
* RTF artifact analysis
* Web shell analysis
* Threat actor correlation
* Vulnerability research
* MITRE based adversary review
* Breach report analysis
* Detection planning

## Tools and Evidence Used

* CyberChef
* ExifTool
* OfficeMalScanner
* RTFScan
* Developer tools
* Threat intelligence reports
* Decoded HTML
* PDF breach reports
* IOC files
* Image metadata
* Password protected archives
* Malware related documents
* Web server artifacts
* MITRE ATT&CK group research
* Public vulnerability research

## Investigation Methodology

### 1. DecodeME Artifact Review

The investigation began with a file named `DecodeME.txt`.

I copied the contents into CyberChef and used the `From Base64` recipe.

The decoded output revealed HTML code that included JavaScript and references to multiple ZIP files.

CyberChef recipe used:

```text
From Base64
```

This showed that the starting artifact was not just random encoded data. It was part of the threat intelligence portal workflow.

### 2. Threat Intelligence Portal Reconstruction

After decoding the HTML, the next step was to submit or combine the decoded HTML with the provided website content so the threat intelligence feed could render correctly.

The rendered page showed three major geographic intelligence markers:

```text
New York
London
Tokyo
```

Each location represented a different intelligence source:

| Location | Intelligence Type | Purpose |
|---|---|---|
| New York | External business commonality | Historical breach comparison |
| London | Internal adversary analysis | Threat actor and asset mapping |
| Tokyo | Cyber activity attribution | Malware and IOC review |

This helped structure the investigation into separate intelligence streams.

### 3. New York Intelligence Review

The New York intelligence source focused on a historical 2017 breach involving a credit reporting agency.

The company identified was:

```text
GenX Finance
```

The country and business model were:

```text
US, Credit Reporting Agency
```

This historical breach was important because it provided business commonality with Haunted Company Inc. Both organizations operated in the credit reporting and financial data space.

### 4. Historical Breach Analysis

The GenX breach report showed that the attacker exploited an application weakness.

Weakness exploited:

```text
Application vulnerability
```

The affected application and CVE were:

```text
Apache Struts
CVE 2017 5638
```

Affected environment:

```text
ACIS
```

Mean Time to Detect:

```text
76 days
```

This showed that public facing application vulnerabilities can remain undetected for long periods and create serious exposure for organizations handling sensitive financial data.

### 5. Data Exposure and Code Weakness Review

The historical breach report also described exposed consumer records and weaknesses in the affected environment.

The report linked the compromise to application flaws and poor data protection.

Important flaws identified included:

```text
SQL injection
Insecure Direct Object Reference
```

Inserted file type:

```text
JSP
```

Attack origin indicator:

```text
China
```

Recommended control:

```text
Network Segmentation
```

This helped show how missing segmentation can allow attackers to move deeper into an environment after gaining access through a vulnerable application.

### 6. London Adversary Analysis

The London intelligence source provided internal adversary analysis and asset threat mapping.

Threat actors reviewed included:

* FIN7
* APT27
* Twisted Spider
* TG 3390

The investigation focused on comparing adversary behavior, motivations, and targeting patterns against the Haunted Company incident.

### 7. FIN7 Analysis

FIN7 was reviewed as a financially motivated threat group.

Key FIN7 details:

| Attribute | Finding |
|---|---|
| Threat group | FIN7 |
| Common threat vector | Ransomware |
| Country association | Russia |
| Motivation | Financial |

This supported the broader analysis because Haunted Company operates in the financial sector and was preparing for an IPO, making financial motivation a realistic concern.

### 8. APT27 Analysis

APT27 was reviewed as another relevant adversary due to finance sector targeting and historical operations.

Key APT27 details:

| Attribute | Finding |
|---|---|
| APT number | APT27 |
| Operation | SharePoint Server Compromise |
| First observed | 2010 |
| Motivation | Espionage |

This helped compare financially motivated activity against espionage driven activity.

### 9. Tokyo IOC Investigation

The Tokyo intelligence source focused on cyber activity attribution and malware artifacts from the compromised server.

The Tokyo IOC archive was password protected, so additional investigation was needed.

The decoded HTML and website source showed references to files such as:

```text
passwords.zip
dp4.jpeg
```

ExifTool was used against the JPEG file to extract metadata.

The image metadata revealed a password in the title field:

```text
youarehaunted!
```

That password was used to open `passwords.zip`, which revealed another password:

```text
hauntedfestival666
```

This allowed access to the remaining IOC files.

### 10. IOC File Review

The extracted IOC material included suspicious files such as:

* RTF document artifact
* ASPX web server file
* IOC text files
* Password protected archive contents

The artifacts suggested two major attack vectors:

```text
Social Engineering
Web shell
```

This was important because it connected user targeting with server side compromise.

### 11. Malicious Document Review

The investigation included analysis of a suspicious RTF document.

The RTF artifact was reviewed using tools such as OfficeMalScanner or RTFScan.

The analysis identified a Process Environment Block related offset:

```text
0xcc
```

This supported deeper malware or exploit analysis from the suspicious document.

### 12. Web Shell and Attribution Review

The web server artifact suggested web shell activity.

Threat actor correlation pointed toward:

```text
Threat Group 3390
China Chopper
```

This mattered because China Chopper is commonly associated with web shell activity and server compromise.

### 13. Vulnerability Research

The final vulnerability research connected the likely remote code execution path to Apache Struts.

Later vulnerability identified:

```text
CVE 2023 50164
```

Attack type:

```text
RCE
```

This aligned with the earlier Apache Struts theme and the web shell activity observed in the Tokyo evidence.

## MITRE ATT&CK Mapping

| Tactic | Technique Focus | Evidence |
|---|---|---|
| Initial Access | Social Engineering | IOC review suggested social engineering as an attack vector |
| Initial Access | Exploit Public Facing Application | Apache Struts vulnerability and web server compromise indicators |
| Execution | Malicious document or server side execution | RTF artifact and ASPX web server file |
| Persistence | Web shell | China Chopper related web shell evidence |
| Defense Evasion | Encoded content | Base64 encoded HTML and hidden file references |
| Credential Access | Password protected IOC chain | Metadata and archive password workflow revealed hidden material |
| Command and Control | Web shell communication | Web shell activity supported remote server access |
| Exfiltration | Sensitive data exposure concern | Historical breach analysis showed data exposure risk |

## Investigation Timeline

| Phase | Activity |
|---|---|
| Initial crisis | Haunted Company website was defaced before the IPO |
| Server attack | Tokyo server came under attack |
| DecodeME review | Base64 content was decoded with CyberChef |
| Portal reconstruction | Decoded HTML revealed threat intelligence markers |
| New York review | Historical GenX breach report was analyzed |
| London review | Internal adversary analysis was reviewed |
| Tokyo review | Malware and IOC artifacts were investigated |
| Metadata analysis | ExifTool revealed a password hidden in image metadata |
| Archive access | Passwords were used to access IOC files |
| Document review | RTF artifact was analyzed for suspicious behavior |
| Web shell review | ASPX artifact supported web shell findings |
| Attribution | Activity correlated to TG 3390 and China Chopper |
| Detection planning | Findings supported pre IPO defensive action |

## Key Findings

The investigation found that:

* The starting artifact decoded into HTML using Base64
* The rendered intel portal contained New York, London, and Tokyo intelligence sources
* The historical breach involved GenX Finance, a US credit reporting agency
* The historical breach exploited an application vulnerability
* Apache Struts and CVE 2017 5638 were key historical findings
* The affected environment was ACIS
* The breach went undetected for 76 days
* The reviewed code flaws included SQL injection and Insecure Direct Object Reference
* A JSP file was inserted during the historical attack
* Network segmentation was identified as a critical control
* FIN7 was reviewed as a financially motivated group
* APT27 was reviewed as an espionage motivated group
* Tokyo IOC artifacts suggested social engineering and web shell activity
* ExifTool helped recover passwords from image metadata
* TG 3390 and China Chopper were linked to the web shell analysis
* CVE 2023 50164 was identified during RCE research

## Defensive Lessons Learned

This lab reinforced several important defensive lessons:

* Threat intelligence requires careful review of all provided sources
* Encoded artifacts can hide important intelligence content
* CyberChef is useful for quickly decoding suspicious data
* Metadata can contain hidden passwords or operational clues
* Password protected archives may be part of the investigation path
* Historical breaches can help identify likely attack patterns
* Public facing application vulnerabilities are major initial access risks
* Web shells are serious persistence and command execution threats
* Adversary attribution requires correlation across multiple sources
* Detection planning should combine IOCs, vulnerabilities, and adversary behavior

## Recommended Defensive Actions

Based on this investigation, recommended actions would include:

* Review public facing web applications for Apache Struts exposure
* Patch systems affected by known Apache Struts vulnerabilities
* Monitor for suspicious JSP and ASPX file creation
* Search web servers for web shell indicators
* Review logs for China Chopper style activity
* Block known malicious infrastructure from IOC files
* Review RTF attachments for suspicious behavior
* Use CyberChef to decode suspicious encoded artifacts
* Inspect metadata of suspicious images and documents
* Improve network segmentation before major business events
* Create detections for web shell uploads and execution
* Review threat intelligence for FIN7, APT27, and TG 3390 related behavior
* Build detections before high visibility events such as an IPO

## What This Project Demonstrates

This project demonstrates my ability to:

* Analyze a threat intelligence based OSINT lab
* Decode Base64 artifacts with CyberChef
* Review HTML and JavaScript source for hidden file references
* Use ExifTool to extract metadata clues
* Use OfficeMalScanner or RTFScan for document analysis
* Review historical breach reports
* Correlate attacker behavior across multiple intelligence sources
* Identify relevant vulnerabilities and attacker methods
* Analyze web shell related artifacts
* Connect threat intelligence to defensive recommendations
* Document findings in a clean technical format

## Disclosure Notice

This writeup is based on an authorized training environment. It is intended to document the investigation process, lab indicators, and defensive concepts learned.

This page does not include private customer data, employer data, production system information, or unauthorized activity.
