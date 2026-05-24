# SOC Simulator: Introduction to Phishing Using Splunk

## Overview

This project documents my completion of the TryHackMe Introduction to Phishing SOC Simulator. The scenario focused on using a SOC simulator environment to monitor alerts, investigate suspicious phishing activity, analyze email and attachment evidence, and create case reports.

The objective was to identify and close all True Positive alerts while documenting the activity clearly enough for a security team to understand the scope, evidence, and malicious behavior.

## Video Walkthrough

[Watch my Introduction to Phishing SOC Simulator walkthrough on YouTube](https://www.youtube.com/watch?v=QBDy7qjsgH8)

## Scenario Summary

The lab introduced a SOC simulator workflow where alerts appeared in a live analyst environment. The goal was to monitor alerts, determine which alerts represented real malicious activity, and close all True Positive alerts.

The scenario focused on:

* Suspicious emails
* Malicious attachments
* Alert review
* Splunk investigation
* Case report writing
* SOC analyst workflow
* True Positive classification
* Evidence documentation

## Objective

The objective of this lab was to:

* Learn how to use SOC Simulator
* Monitor and analyze live alerts
* Investigate suspicious emails
* Review attachments and related evidence
* Identify malicious activity
* Document critical events
* Create detailed case reports
* Close all True Positive alerts
* Practice SOC analyst decision making

## Key Investigation Data

| Evidence Type | Finding |
|---|---|
| Platform | TryHackMe |
| Lab name | Introduction to Phishing SOC Simulator |
| Main tool | Splunk |
| Scenario type | SOC simulator |
| Main focus | Phishing investigation |
| Alert goal | Close all True Positive alerts |
| Evidence reviewed | Suspicious emails and attachments |
| Analyst task | Monitor, investigate, document, and close alerts |
| Final output | Case reports based on observed malicious activity |

## Skills Demonstrated

* SOC alert triage
* Phishing investigation
* Splunk analysis
* Email security review
* Attachment analysis
* Evidence documentation
* True Positive classification
* Case report writing
* Alert closure workflow
* Analyst decision making
* Incident communication
* Security operations workflow

## Tools and Evidence Used

* Splunk
* TryHackMe SOC Simulator
* Alert queue
* Suspicious email evidence
* Attachment evidence
* Case report fields
* Alert classification workflow
* Event review
* Search and investigation workflow

## Investigation Methodology

### 1. Alert Monitoring

The investigation began by reviewing alerts in the SOC Simulator environment.

The goal was to determine which alerts required investigation and which alerts represented real malicious activity.

During alert monitoring, I focused on:

* Alert title
* Alert severity
* Related user or mailbox
* Suspicious email details
* Attachment indicators
* Event context
* Evidence available for review

### 2. Suspicious Email Review

The phishing investigation required reviewing email related evidence to determine whether the activity was malicious.

I looked for:

* Suspicious sender details
* Unexpected message content
* Urgent or manipulative language
* Suspicious attachment names
* Unusual links or file behavior
* Signs of impersonation
* Indicators that the email was designed to trick the recipient

This helped determine whether the alert should be classified as a True Positive.

### 3. Attachment Analysis

Attachments were reviewed as part of the investigation because phishing emails often use files to deliver malware, steal credentials, or trick users into enabling risky behavior.

The review focused on:

* Attachment name
* File type
* Relationship to the email message
* Whether the attachment matched the sender context
* Whether the attachment appeared suspicious
* Whether the evidence supported malicious classification

### 4. Splunk Investigation

Splunk was used to review alert evidence and support the investigation.

The Splunk workflow helped identify:

* Related events
* Email related activity
* Alert context
* User activity
* Time based evidence
* Indicators connected to the alert

This helped move the investigation beyond the alert summary and into the supporting event data.

### 5. True Positive Classification

The main goal of the lab was to close all True Positive alerts.

A True Positive classification was used when the evidence showed real malicious or suspicious activity that required action.

The decision was based on:

* Email evidence
* Attachment evidence
* Alert context
* Splunk events
* Whether the activity matched phishing behavior
* Whether the event required documentation and closure

### 6. Case Report Writing

After validating the alert, I created a case report to document the investigation.

The case report focused on:

* What happened
* Which user or mailbox was involved
* What evidence supported the finding
* Why the alert was classified as True Positive
* What malicious activity was observed
* What action was taken
* What another analyst should know if reviewing the case later

This helped reinforce that SOC work is not only about finding malicious activity. It is also about writing clear reports that support team understanding and future response.

## Investigation Timeline

| Phase | Activity |
|---|---|
| Alert generated | SOC Simulator produced phishing related alerts |
| Alert review | Alert details were reviewed for context |
| Email review | Suspicious messages were analyzed |
| Attachment review | File evidence was reviewed for suspicious behavior |
| Splunk investigation | Supporting events were searched and reviewed |
| Classification | True Positive alerts were identified |
| Documentation | Case reports were created |
| Closure | True Positive alerts were closed |

## Key Findings

The lab showed that:

* Phishing alerts require careful evidence review
* Suspicious emails should be analyzed in context
* Attachments can provide important evidence of malicious intent
* Splunk helps validate alert details through event data
* True Positive alerts should be documented clearly
* Case reports help other analysts understand the full scope of an alert
* SOC Simulator is useful for practicing real analyst workflow

## Defensive Lessons Learned

This lab reinforced several important defensive lessons:

* Alert summaries are not enough by themselves
* Analysts should review supporting event evidence before closing alerts
* Email sender details and attachment context matter during phishing analysis
* True Positive classification requires evidence
* Case reports should be clear, specific, and useful to the team
* SOC analysts need both technical investigation skills and documentation skills
* Practicing alert closure builds confidence for real SOC work

## Recommended Defensive Actions

Based on this lab, recommended actions would include:

* Review suspicious emails before users interact with them
* Block confirmed malicious senders or domains
* Quarantine malicious attachments when identified
* Search for other users who received the same message
* Review email gateway logs for similar phishing attempts
* Create clear case reports for confirmed phishing activity
* Tune detections based on repeated phishing patterns
* Train users to report suspicious emails quickly
* Use Splunk searches to validate alert evidence
* Standardize alert closure procedures

## What This Project Demonstrates

This project demonstrates my ability to:

* Work through a SOC simulator phishing scenario
* Monitor and triage alerts
* Use Splunk during alert investigation
* Analyze suspicious email activity
* Review attachment based evidence
* Identify True Positive alerts
* Create useful case reports
* Close alerts based on evidence
* Apply SOC analyst workflow in a training environment
* Communicate findings clearly for a security team

## Disclosure Notice

This writeup is based on an authorized TryHackMe SOC Simulator training environment. It is intended to document the investigation process, lab skills, and defensive concepts learned.

This page does not include private customer data, employer data, production system information, or unauthorized activity.
