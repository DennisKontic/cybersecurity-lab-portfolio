---
layout: project
title: HTB CDSA Enterprise Intrusion Analysis
---
# Enterprise Intrusion Analysis and Incident Response: HTB CDSA

## Overview

This project summarizes my experience completing the Hack The Box Certified Defensive Security Analyst (HTB CDSA) certification assessment. The HTB CDSA is a practical defensive security certification focused on security analysis, SOC operations, incident handling, threat hunting, digital forensics, SIEM investigation, network traffic analysis, malware analysis, and professional incident reporting.

The assessment required analyzing a simulated enterprise compromise in an authorized Hack The Box lab environment. The goal was to investigate suspicious activity, correlate evidence across multiple data sources, identify attacker behavior, determine business impact, and produce a professional incident report.

Due to Hack The Box certification rules and terms of service, this writeup does not include exam answers, flags, exact hostnames, IP addresses, screenshots, private artifacts, step by step solutions, or any sensitive exam details. Instead, this page documents the skills, methodology, and defensive concepts demonstrated during the assessment.

## Objective

The objective of this project was to perform a complete defensive security investigation by:

* Reviewing alerts, logs, and forensic evidence
* Identifying suspicious and malicious activity
* Correlating events across multiple systems and data sources
* Reconstructing the attacker timeline
* Mapping observed behavior to security frameworks
* Determining the scope and impact of the incident
* Producing a professional incident report with remediation guidance

## Skills Demonstrated

* SOC alert triage
* Security event investigation
* SIEM analysis
* Incident response methodology
* Digital forensics fundamentals
* Threat hunting
* Windows and Linux log analysis
* Network traffic analysis
* Active Directory attack analysis
* Malware behavior analysis
* Evidence correlation
* Timeline reconstruction
* MITRE ATT&CK mapping
* Cyber Kill Chain analysis
* Remediation planning based on risk
* Professional incident reporting

## Tools and Concepts Used

* SIEM investigation workflows
* Elastic and ELK log analysis
* Splunk search methodology
* Windows Event Logs
* Sysmon telemetry
* Network traffic analysis
* IDS and IPS concepts
* Endpoint investigation
* Authentication log review
* Web attack analysis
* Malware analysis concepts
* MITRE ATT&CK
* Cyber Kill Chain
* Incident handling lifecycle
* Reporting based on evidence

## Methodology

### 1. Initial Triage

The investigation began by reviewing available alerts, logs, and evidence to determine whether the activity represented benign behavior, suspicious activity, or a confirmed security incident.

The initial triage phase focused on identifying:

* Suspicious authentication activity
* Unusual network connections
* Potential malware execution
* Abnormal process behavior
* Web attack indicators
* Signs of lateral movement
* Evidence of command and control
* Possible data exfiltration activity

### 2. Evidence Collection and Review

After identifying suspicious activity, I reviewed the available evidence across multiple sources to understand what occurred and which systems were affected.

Evidence types included:

* Authentication logs
* Endpoint activity
* Network traffic indicators
* Web request patterns
* Security alerts
* Process and execution artifacts
* Potential malware behavior
* Indicators of compromise

The focus was not only on finding isolated suspicious events, but also on connecting those events into a complete incident narrative.

### 3. Correlation and Timeline Reconstruction

A major part of the assessment involved correlating separate pieces of evidence to reconstruct the attack timeline.

This included identifying:

* Initial access activity
* Execution behavior
* Persistence or continued activity
* Privilege escalation indicators
* Lateral movement attempts
* Command and control communication
* Data access or exfiltration indicators
* Impact to affected systems

This process helped determine how the attacker moved through the environment and what defensive gaps may have allowed the activity to progress.

### 4. ATT&CK and Kill Chain Mapping

Observed attacker behavior was mapped to common defensive frameworks to organize the investigation and communicate findings clearly.

Example mapping areas included:

* Initial Access: how the attacker may have entered the environment
* Execution: how malicious or suspicious activity was run
* Persistence: whether the attacker attempted to maintain access
* Privilege Escalation: whether higher privileges were attempted or obtained
* Defense Evasion: whether the attacker attempted to avoid detection
* Credential Access: whether credentials may have been targeted
* Discovery: whether internal enumeration occurred
* Lateral Movement: whether the attacker moved between systems
* Command and Control: whether external communication was observed
* Exfiltration: whether data may have been staged or transferred
* Impact: whether availability, integrity, or confidentiality was affected

Specific exam evidence and answers are intentionally omitted.

### 5. Findings and Impact Analysis

The investigation required identifying the most important findings and explaining their potential impact to the organization.

The analysis focused on:

* Which systems were affected
* What attacker activity was confirmed
* Which events were suspicious but required further validation
* What evidence supported each finding
* What the likely business impact was
* Which remediation steps should be prioritized

The goal was to avoid unsupported assumptions and document findings based on available evidence.

### 6. Incident Report Development

A final professional incident report was created to communicate the investigation results. The report was written for both technical and general audiences.

The report included:

* Executive summary
* Incident timeline
* Affected systems
* Key findings
* Evidence summary
* Attack behavior analysis
* Risk and impact assessment
* Remediation recommendations
* Defensive improvement opportunities

## Key Takeaways

This project strengthened my ability to investigate incidents from a defender’s perspective. The most valuable part of the assessment was learning how to correlate separate data sources into a complete incident narrative instead of treating alerts as isolated events.

The assessment also reinforced the importance of clear reporting. Finding evidence is only one part of the job. A defensive analyst must also explain what happened, why it matters, how serious it is, and what the organization should do next.

## What This Project Demonstrates

This project demonstrates my ability to:

* Investigate suspicious activity in a realistic enterprise lab
* Analyze alerts, logs, network activity, and endpoint evidence
* Correlate multiple sources of evidence
* Reconstruct attacker behavior
* Think through incident scope and impact
* Apply MITRE ATT&CK and Cyber Kill Chain concepts
* Communicate findings in a professional incident report
* Recommend practical remediation actions

## Disclosure Notice

This writeup intentionally avoids disclosing protected HTB exam content. It does not include flags, exact questions, answers, hostnames, IP addresses, screenshots, exploitation paths, private artifacts, or step by step exam solutions.

The purpose of this page is to document the defensive security skills demonstrated through the certification while respecting Hack The Box certification rules and maintaining the integrity of the exam.
