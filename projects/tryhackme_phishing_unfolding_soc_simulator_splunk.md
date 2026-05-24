# SOC Simulator: Phishing Unfolding Using Splunk

## Overview

This project documents my completion of the TryHackMe Phishing Unfolding SOC Simulator. The scenario focused on analyzing a live phishing attack as it unfolded inside a corporate network.

The lab required monitoring alerts, reviewing suspicious activity, analyzing PowerShell execution, identifying reverse shell behavior, investigating suspicious DNS requests, and creating case reports to document the full attack chain.

## Video Walkthrough

[Watch my Phishing Unfolding SOC Simulator walkthrough on YouTube](https://www.youtube.com/watch?v=LP1XFOKkGAQ)

## Scenario Summary

The scenario placed me in the role of a SOC analyst responding to an active phishing incident. The attack unfolded across multiple stages, requiring careful review of alerts, logs, command activity, network connections, and DNS behavior.

The goal was to piece together the attack chain as it happened and document the evidence clearly enough for the security team to understand the full scope of the breach.

The scenario focused on:

* Phishing activity
* PowerShell execution
* Reverse shell connections
* Suspicious DNS requests
* Alert triage
* Splunk investigation
* Attack chain reconstruction
* Case report writing
* SOC analyst decision making

## Objective

The objective of this lab was to:

* Monitor and analyze active security alerts
* Investigate phishing related activity
* Identify suspicious PowerShell execution
* Detect possible reverse shell behavior
* Review suspicious DNS requests
* Reconstruct the attack chain
* Document critical events
* Create detailed case reports
* Communicate the full scope of malicious activity
* Practice SOC analyst workflows under pressure

## Key Investigation Data

| Evidence Type | Finding |
|---|---|
| Platform | TryHackMe |
| Lab name | Phishing Unfolding SOC Simulator |
| Main tool | Splunk |
| Scenario type | SOC simulator |
| Main focus | Live phishing attack investigation |
| Key activity | PowerShell execution |
| Network concern | Reverse shell connections |
| DNS concern | Suspicious DNS requests |
| Analyst output | Case reports |
| Main goal | Reconstruct and document the full attack chain |

## Skills Demonstrated

* SOC alert triage
* Splunk investigation
* Phishing analysis
* PowerShell activity review
* Reverse shell detection
* Suspicious DNS investigation
* Attack chain reconstruction
* Case report writing
* Incident documentation
* Timeline analysis
* Evidence based alert classification
* Security operations communication
* Threat behavior analysis

## Tools and Evidence Used

* Splunk
* TryHackMe SOC Simulator
* Alert queue
* PowerShell logs
* DNS request logs
* Network connection evidence
* Case report workflow
* Timeline evidence
* Suspicious command activity
* Security event data

## Investigation Methodology

### 1. Alert Monitoring

The investigation began by monitoring alerts in the SOC Simulator environment.

The goal was to identify which alerts represented meaningful malicious activity and which events needed deeper investigation.

During alert monitoring, I focused on:

* Alert title
* Alert severity
* Source host
* Affected user
* Related process activity
* Network indicators
* DNS activity
* Time sequence of events

This helped establish the starting point for the investigation.

### 2. Phishing Activity Review

The incident began with phishing related activity. I reviewed the available evidence to understand how the attacker may have gained initial access.

The phishing review focused on:

* Suspicious message activity
* User interaction
* Possible malicious attachment or link behavior
* Activity occurring shortly after the phishing event
* Signs that the user system began executing suspicious commands

This helped connect the phishing stage to later host and network activity.

### 3. PowerShell Execution Analysis

PowerShell activity was one of the critical events in the attack chain.

The investigation focused on identifying whether PowerShell was used for suspicious execution, payload retrieval, command activity, or attacker control.

PowerShell review included:

* Command line activity
* Parent and child process context
* Execution timing
* Script behavior
* Suspicious parameters
* Relationship to phishing activity
* Connection to later network behavior

PowerShell activity was important because attackers often use it for execution, download activity, defense evasion, and remote control.

### 4. Reverse Shell Connection Review

The lab required identifying possible reverse shell behavior.

The investigation focused on reviewing network connections that could indicate a compromised host reaching out to attacker infrastructure.

I looked for:

* Unusual outbound connections
* Suspicious destination IP addresses or domains
* Unexpected ports
* Network activity after PowerShell execution
* Connections that looked interactive or command driven
* Timing that aligned with the attack chain

Reverse shell behavior was a major concern because it can give an attacker remote control over the affected system.

### 5. Suspicious DNS Request Analysis

Suspicious DNS requests were reviewed to identify possible command and control infrastructure, staging domains, or attacker controlled resources.

DNS analysis focused on:

* Unusual domains
* Repeated DNS lookups
* Newly observed destinations
* Domains tied to suspicious process activity
* DNS requests occurring after phishing or PowerShell execution
* Possible beaconing or payload retrieval behavior

DNS evidence helped support the broader timeline of the attack.

### 6. Attack Chain Reconstruction

After reviewing alerts, PowerShell events, reverse shell connections, and DNS requests, I reconstructed the attack chain.

The goal was to show how each event connected to the next instead of treating alerts as isolated findings.

The attack chain focused on:

* Initial phishing activity
* User interaction
* PowerShell execution
* Suspicious network connection
* Reverse shell behavior
* DNS activity
* Confirmed malicious behavior
* Case documentation

### 7. Case Report Writing

The final step was creating detailed case reports based on the observed evidence.

The case reports documented:

* What happened
* Which systems or users were involved
* What suspicious commands were observed
* What network behavior occurred
* What DNS requests were suspicious
* Why the activity was malicious
* What the likely attacker objective was
* What actions the team should take next

This reinforced that SOC analysts must be able to explain incidents clearly, not just identify technical indicators.

## Attack Timeline

| Phase | Activity |
|---|---|
| Initial alert | SOC Simulator generated phishing related alerts |
| Phishing activity | User activity indicated possible phishing interaction |
| Execution | Suspicious PowerShell activity was observed |
| Network activity | Outbound connections suggested possible attacker control |
| Reverse shell concern | Reverse shell behavior was investigated |
| DNS review | Suspicious DNS requests were analyzed |
| Correlation | Events were connected into a full attack chain |
| Documentation | Case reports were created to explain the breach |

## Key Findings

The lab showed that:

* Phishing can quickly lead to host based execution
* PowerShell activity should be reviewed carefully during phishing investigations
* Reverse shell behavior can appear through suspicious outbound connections
* DNS requests can reveal attacker infrastructure or staging behavior
* Splunk is useful for correlating events across the attack chain
* Case reports help the team understand the full scope of the breach
* SOC analysts need to document evidence clearly during active investigations

## Defensive Lessons Learned

This lab reinforced several important defensive lessons:

* Phishing alerts should be investigated beyond the email itself
* PowerShell logs are critical for identifying post phishing execution
* Reverse shell behavior should be detected through outbound connection analysis
* DNS logs can provide early signs of command and control activity
* Attack chain reconstruction is more valuable than isolated alert review
* Case reports should explain what happened, why it matters, and what to do next
* Real SOC work requires both technical investigation and clear communication

## Recommended Defensive Actions

Based on this lab, recommended actions would include:

* Review phishing alerts for follow on execution activity
* Monitor PowerShell command line activity
* Alert on suspicious PowerShell parameters and encoded commands
* Review outbound network connections after phishing events
* Detect reverse shell patterns where possible
* Monitor suspicious DNS requests
* Block confirmed malicious domains and IP addresses
* Search for other hosts with similar DNS or network activity
* Create case reports for confirmed malicious activity
* Escalate confirmed incidents for containment and remediation
* Tune detections based on observed phishing attack chains

## What This Project Demonstrates

This project demonstrates my ability to:

* Work through a SOC simulator phishing scenario
* Use Splunk to investigate suspicious activity
* Analyze PowerShell execution
* Investigate reverse shell behavior
* Review suspicious DNS requests
* Reconstruct an attack chain
* Document critical events
* Create detailed case reports
* Explain malicious activity clearly
* Apply SOC analyst workflows in a live simulation environment

## Disclosure Notice

This writeup is based on an authorized TryHackMe SOC Simulator training environment. It is intended to document the investigation process, lab skills, and defensive concepts learned.

This page does not include private customer data, employer data, production system information, or unauthorized activity.
