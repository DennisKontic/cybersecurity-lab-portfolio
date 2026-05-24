# Tusk InfoStealer Threat Intelligence Lab

## Overview

This project documents my investigation of the Tusk InfoStealer lab. The scenario involved a blockchain development company that detected unusual activity after an employee was redirected to an unfamiliar website while accessing a DAO management platform.

Soon after the redirect, multiple cryptocurrency wallets linked to the organization were drained. The investigation focused on analyzing threat intelligence, reviewing malware configuration details, identifying indicators of compromise, understanding attacker tactics, and tracking cryptocurrency movement tied to the campaign.

## Video Walkthrough

[Watch my Tusk InfoStealer Lab walkthrough on YouTube](https://www.youtube.com/watch?v=o0jAfW0V6pM)

## Scenario Summary

A blockchain development company observed suspicious activity after an employee was redirected to an unfamiliar website during normal access to a DAO management platform.

Shortly after the redirect, several organization linked cryptocurrency wallets were drained. Investigators suspected that a malicious tool was used to steal credentials, collect sensitive data, and support the theft of cryptocurrency assets.

The investigation required analyzing threat intelligence sources to understand the attack method, identify infrastructure, extract indicators, and follow the movement of stolen funds.

## Objective

The objective of this investigation was to:

* Analyze threat intelligence related to the Tusk InfoStealer campaign
* Identify attacker tactics, techniques, and procedures
* Review malware configuration details
* Extract indicators of compromise
* Identify malicious infrastructure
* Analyze suspicious domains, hashes, and related artifacts
* Understand how credentials may have been stolen
* Track cryptocurrency flow linked to the incident
* Document findings in a clear threat intelligence format

## Key Investigation Data

| Evidence Type | Finding |
|---|---|
| Lab name | Tusk InfoStealer |
| Category | Threat Intel |
| Affected organization type | Blockchain development company |
| Initial activity | Employee redirected to unfamiliar website |
| Targeted platform type | DAO management platform |
| Main impact | Cryptocurrency wallets drained |
| Suspected malware type | InfoStealer |
| Main investigation focus | Threat intelligence, malware configuration, IOCs, crypto flow |
| Tools used | Kaspersky Threat Intelligence Portal, Threat Intelligence Reports, VirusTotal |
| Video walkthrough | Available on YouTube |

## Skills Demonstrated

* Threat intelligence analysis
* Malware configuration review
* Indicator extraction
* IOC enrichment
* VirusTotal investigation
* Kaspersky Threat Intelligence Portal usage
* Threat report analysis
* Cryptocurrency theft investigation
* Wallet activity review
* Infrastructure tracking
* TTP identification
* Campaign analysis
* Incident documentation
* Defensive reporting

## Tools and Evidence Used

* Kaspersky Threat Intelligence Portal
* Threat intelligence reports
* VirusTotal
* Malware configuration details
* File hashes
* Domains
* URLs
* IP addresses
* Cryptocurrency wallet addresses
* Blockchain transaction information
* Campaign reporting
* IOC enrichment sources

## Investigation Methodology

### 1. Initial Threat Intelligence Review

The investigation began by reviewing the scenario and identifying the major investigative leads.

The key starting points were:

* The unfamiliar website redirect
* The DAO management platform connection
* The drained cryptocurrency wallets
* The suspected InfoStealer malware activity
* The need to identify attacker infrastructure

This helped frame the investigation as both a malware analysis and threat intelligence problem.

### 2. Malware Family and Campaign Review

The next step was to review intelligence related to the Tusk InfoStealer campaign.

The focus was on understanding:

* How the malware was delivered
* What type of data the malware attempted to steal
* What infrastructure was associated with the campaign
* Which indicators were linked to the activity
* How the campaign targeted cryptocurrency related victims

This helped connect the observed incident to a broader threat campaign rather than treating it as an isolated event.

### 3. Indicator Collection

Indicators of compromise were collected and reviewed from threat intelligence sources.

The investigation focused on identifying:

* Malicious domains
* Suspicious URLs
* File hashes
* IP addresses
* Malware configuration values
* Wallet addresses
* Infrastructure connected to the campaign

These indicators helped support detection, blocking, and further hunting across security tools.

### 4. VirusTotal Enrichment

VirusTotal was used to enrich suspicious indicators and better understand relationships between files, domains, URLs, and infrastructure.

The review focused on:

* Detection names
* Community intelligence
* Related files
* Contacted domains
* Contacted URLs
* Associated IP addresses
* File reputation
* Behavioral context

VirusTotal helped provide quick validation of suspicious artifacts and supported pivoting between related indicators.

### 5. Kaspersky Threat Intelligence Portal Review

Kaspersky Threat Intelligence Portal was used to review reputation, malware context, and campaign related intelligence.

The portal helped support:

* Malware family confirmation
* IOC enrichment
* Infrastructure review
* Threat actor or campaign context
* Related artifact discovery
* Confidence building around suspicious indicators

This helped strengthen the analysis beyond a single source of evidence.

### 6. Malware Configuration Analysis

The malware configuration was reviewed to identify useful values that could support detection and response.

Configuration review focused on:

* Command and control infrastructure
* URLs or domains used by the malware
* Data theft behavior
* Credential collection behavior
* Possible exfiltration destinations
* Campaign specific values
* Related infrastructure indicators

The purpose of reviewing the configuration was to understand how the malware operated and what defenders could search for in logs and endpoint telemetry.

### 7. Cryptocurrency Flow Analysis

Because the scenario involved drained wallets, the investigation also required reviewing cryptocurrency flow.

The goal was to understand:

* Which wallets were affected
* Where funds were transferred
* Whether funds moved through additional wallets
* Whether any wallet addresses were linked to known malicious activity
* How the funds movement supported the overall incident timeline

This helped connect the malware activity to the financial impact of the attack.

### 8. TTP Identification

The attacker behavior was reviewed to identify tactics, techniques, and procedures.

The investigation focused on:

* Initial redirection to unfamiliar infrastructure
* Credential theft behavior
* Use of an InfoStealer
* Infrastructure used to support the campaign
* Data collection and exfiltration behavior
* Cryptocurrency theft and movement

This helped translate raw indicators into a clearer understanding of attacker behavior.

## MITRE ATT&CK Mapping

| Tactic | Technique Focus | Evidence |
|---|---|---|
| Initial Access | Malicious redirect or phishing style access path | Employee was redirected to an unfamiliar website while accessing a DAO management platform |
| Execution | Malware execution | Suspicious tool believed to be responsible for credential theft and wallet compromise |
| Credential Access | Credential theft | InfoStealer activity suggested credential collection from the victim environment |
| Collection | Sensitive data collection | Malware likely collected credentials or wallet related data |
| Command and Control | External infrastructure communication | Threat intelligence review focused on attacker infrastructure |
| Exfiltration | Data theft | Malware activity supported theft of sensitive information |
| Impact | Cryptocurrency theft | Multiple organization linked wallets were drained |

## Attack Timeline

| Phase | Activity |
|---|---|
| User activity | Employee accessed a DAO management platform |
| Redirect | Employee was redirected to an unfamiliar website |
| Malware concern | Suspicious tool was believed to be involved |
| Credential theft | InfoStealer activity likely collected sensitive access material |
| Wallet compromise | Organization linked wallets were drained |
| Threat intelligence review | Indicators and infrastructure were analyzed |
| Cryptocurrency tracking | Wallet movement was reviewed to understand financial impact |
| Defensive reporting | Findings were documented for detection and response |

## Key Findings

The investigation found that:

* The incident involved activity consistent with an InfoStealer campaign
* The victim organization was targeted in a cryptocurrency related context
* The initial lead involved a redirect from a DAO management workflow
* Threat intelligence sources were needed to understand the campaign
* VirusTotal helped enrich suspicious indicators
* Kaspersky Threat Intelligence Portal helped review malware and infrastructure context
* Malware configuration details were important for identifying attacker infrastructure
* Cryptocurrency wallet activity helped show the financial impact of the attack
* IOC extraction was critical for detection and response

## Defensive Lessons Learned

This lab reinforced several important defensive lessons:

* Cryptocurrency organizations are attractive targets for credential theft
* Redirects from trusted workflows should be investigated quickly
* InfoStealer malware can lead directly to financial loss
* Threat intelligence helps connect isolated indicators to larger campaigns
* Malware configuration can expose command and control infrastructure
* IOC enrichment should use multiple sources when possible
* Wallet activity can provide important evidence during crypto theft investigations
* Defenders should monitor for suspicious domain access, credential theft behavior, and unusual wallet activity

## Recommended Defensive Actions

Based on this investigation, recommended actions would include:

* Block identified malicious domains and URLs
* Block file hashes linked to the Tusk InfoStealer campaign
* Review endpoint telemetry for execution of suspicious files
* Search proxy and DNS logs for campaign infrastructure
* Review authentication logs for suspicious access after the redirect
* Rotate credentials for affected users
* Revoke active sessions and tokens
* Review access to cryptocurrency wallet management systems
* Enforce MFA on sensitive platforms
* Review browser stored credentials exposure
* Monitor wallet activity for suspicious transfers
* Use threat intelligence to hunt for related indicators
* Educate staff on suspicious redirects and fake platform pages

## What This Project Demonstrates

This project demonstrates my ability to:

* Analyze a threat intelligence based malware case
* Review InfoStealer behavior
* Use VirusTotal for IOC enrichment
* Use Kaspersky Threat Intelligence Portal for campaign context
* Extract useful indicators from threat reports
* Review malware configuration details
* Connect malware activity to cryptocurrency theft
* Track suspicious wallet movement
* Identify attacker tactics and infrastructure
* Translate threat intelligence findings into defensive actions
* Document an investigation clearly for a technical portfolio

## Disclosure Notice

This writeup is based on an authorized lab and training environment. It is intended to document the investigation process, lab indicators, and defensive concepts learned.

This page does not include private customer data, employer data, production system information, or unauthorized activity.
