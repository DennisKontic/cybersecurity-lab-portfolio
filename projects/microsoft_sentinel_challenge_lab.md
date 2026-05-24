# Microsoft Sentinel Challenge Lab

## Overview

This project documents my completion of a Microsoft Sentinel challenge lab focused on SOC analyst incident investigation and threat hunting. The lab involved reviewing incidents, taking ownership, investigating alerts, analyzing entities, using Log Analytics, and escalating an incident for deeper threat hunting.

The goal of this project was to practice how a SOC analyst works inside Microsoft Sentinel during incident triage, investigation, management, and escalation.

## Video Walkthrough

[Watch my Microsoft Sentinel Challenge Lab walkthrough on YouTube](https://www.youtube.com/watch?v=_WLV1P0QLbg)

## Scenario Summary

In this lab, previously enabled Microsoft Sentinel analytics rules generated multiple incidents in a cloud security environment. Acting as a SOC Level 1 analyst, I reviewed open incidents, took ownership of an incident, investigated alert evidence, reviewed entities, checked geolocation data, and created a task for SOC Level 2 threat hunting.

The lab focused on:

* Incident triage
* Alert investigation
* Microsoft Sentinel incident management
* Log Analytics review
* Entity analysis
* Incident ownership
* Status updates
* Task creation
* Escalation to SOC Level 2
* Threat hunting preparation

## Objective

The objective of this lab was to:

* Understand the difference between events, alerts, and incidents
* Review open incidents in Microsoft Sentinel
* Take ownership of an incident
* Change incident status from New to Active
* Investigate alert evidence inside an incident
* Use Link to LA to review alert logs
* Analyze entities such as IP addresses and accounts
* Review geolocation information
* Create incident tasks
* Escalate an incident to SOC Level 2 analysts
* Understand incident closure classifications

## Key Investigation Data

| Evidence Type | Finding |
|---|---|
| Platform | TryHackMe |
| Lab focus | Microsoft Sentinel incident investigation |
| Cloud platform | Microsoft Azure |
| Security tool | Microsoft Sentinel |
| Role | SOC Level 1 Analyst |
| Escalation target | SOC Level 2 Analysts |
| Incidents reviewed | 3 open incidents |
| Incident selected | Solorigate |
| Solorigate MITRE tactic | Command and Control |
| Disabled account incident | Sign ins from IPs that attempt sign ins to disabled accounts |
| IP entity | `175.45.176.99` |
| Reported geolocation value | Korea |
| Targeted disabled account | `johns@m365x816222.onmicrosoft.com` |
| Login attempts | `4` |
| Log investigation feature | Link to LA |
| Visual investigation query type | Exploration queries |

## Skills Demonstrated

* Microsoft Sentinel incident triage
* Incident ownership and management
* Alert investigation
* Log Analytics investigation
* Entity analysis
* IP geolocation review
* Threat hunting preparation
* Incident escalation
* SOC workflow understanding
* Event, alert, and incident classification
* Incident task creation
* Closure classification understanding
* Cloud security investigation

## Tools and Evidence Used

* Microsoft Sentinel
* Microsoft Azure
* Log Analytics
* Analytics rules
* Incident timeline
* Incident details page
* Link to LA
* Entity pane
* IP geolocation enrichment
* Activity log
* Incident tasks
* Microsoft Defender style incident sources
* MITRE ATT&CK tactic mapping

## Investigation Methodology

### 1. Event, Alert, and Incident Review

The lab began by reviewing the difference between events, alerts, and incidents.

An event is normal activity that happens at a point in time. An alert is activity that meets a defined threshold or rule condition and requires review. An incident is a negative event or group of alerts that may disrupt normal operations and requires investigation.

This distinction matters because SOC analysts need to understand whether they are reviewing raw activity, a triggered alert, or a larger incident that requires response.

### 2. Incident Overview Review

I reviewed the Microsoft Sentinel incidents page to understand the number of open, new, and active incidents.

The incident overview helped identify:

* Incident name
* Owner
* Status
* Severity
* Related alerts
* Related evidence
* MITRE tactics and techniques
* Incident source
* Initial investigation context

This helped determine which incident required ownership and deeper analysis.

### 3. Taking Ownership

As part of the SOC workflow, I took ownership of the Solorigate incident.

This involved:

* Assigning the incident to my lab user
* Changing the status from New to Active
* Reviewing the incident description
* Checking the activity log for recent changes
* Preparing the incident for deeper investigation

Taking ownership is important because every incident should have a clear analyst responsible for investigation and updates.

### 4. Incident Details Review

After taking ownership, I opened the full incident details page.

The incident details page provided access to:

* Incident timeline
* Alerts
* Entities
* Logs
* Tasks
* Activity log
* Investigation options

This page acted as the central location for reviewing the incident and deciding whether it needed escalation.

### 5. Timeline and Alert Review

I reviewed the incident timeline to understand the sequence of related alerts.

The timeline helped show:

* When alerts occurred
* Which alerts contributed to the incident
* Severity of related activity
* Possible attacker behavior
* Where deeper log review was needed

This helped connect individual alerts to the larger incident context.

### 6. Log Analytics Review

To investigate alert evidence without leaving the incident details page, I used:

```text
Link to LA
```

This opened the Log Analytics view in the context of the selected alert.

Using logs allowed deeper review of:

* Alert triggering events
* Related accounts
* IP addresses
* Disabled account activity
* Event fields
* Suspicious login attempts

This was important because the incident summary alone was not enough to fully understand the evidence.

### 7. Entity Analysis

Microsoft Sentinel identified entities related to the incident, including IP addresses and accounts.

One key IP entity involved in the disabled account incident was:

```text
175.45.176.99
```

The reported geolocation value for this IP was:

```text
Korea
```

Entity analysis helped provide more context about suspicious activity and supported the decision to escalate the incident for deeper threat hunting.

### 8. Disabled Account Investigation

One incident involved sign ins from IP addresses attempting to access disabled accounts.

The targeted disabled account was:

```text
johns@m365x816222.onmicrosoft.com
```

The number of login attempts was:

```text
4
```

This type of activity can indicate password spraying, credential stuffing, automated login attempts, or reconnaissance against identity infrastructure.

### 9. Task Creation and Escalation

After reviewing the available evidence, I created a task for SOC Level 2 analysts to perform deeper threat hunting.

The incident was then assigned to the SOC Level 2 group for additional investigation.

This step reinforced how SOC teams use structured workflows to hand off incidents when deeper analysis is required.

### 10. Incident Closure Classification Review

The lab also covered incident closure classifications.

Important closure types included:

| Classification | Meaning |
|---|---|
| True Positive | Actual threat activity occurred |
| Benign Positive | Activity was real but expected, such as red team activity |
| False Positive | Alert data or logic was inaccurate |
| Undetermined | Not enough information was available to make a final determination |

The lab reinforced that incidents should ideally be closed with a clear root cause instead of leaving them undetermined.

## Microsoft Sentinel Concepts Practiced

| Concept | What It Means |
|---|---|
| Event | Normal activity captured at a point in time |
| Alert | Activity that triggered a detection rule or threshold |
| Incident | A security issue requiring investigation |
| Owner | Analyst responsible for handling the incident |
| Status | New, Active, or Closed |
| Severity | Informational, Low, Medium, or High |
| Tasks | Standardized actions assigned during incident handling |
| Entities | Recognized data items such as accounts, hosts, IPs, URLs, malware, or processes |
| Link to LA | Opens Log Analytics in the context of the alert |
| Exploration queries | Queries used during visual investigation to deepen entity analysis |

## Attack and Investigation Timeline

| Phase | Activity |
|---|---|
| Incident generation | Analytics rules generated incidents in Microsoft Sentinel |
| Triage | Open incidents were reviewed |
| Ownership | Solorigate incident was assigned to the analyst |
| Status update | Incident status was changed from New to Active |
| Timeline review | Related alerts were reviewed in the incident timeline |
| Log review | Link to LA was used to inspect alert logs |
| Entity review | IP and account entities were analyzed |
| Disabled account analysis | Login attempts against disabled account were reviewed |
| Escalation | Task was created for SOC Level 2 threat hunting |
| Handoff | Incident was assigned to SOC Level 2 Analysts |

## Key Findings

The lab showed that:

* Microsoft Sentinel can collect incidents from multiple security sources
* Incidents should be assigned to an owner before deeper investigation
* Incident status should reflect the current investigation state
* The incident timeline helps analysts understand alert sequence
* Link to LA allows analysts to investigate alert logs without losing context
* Entities provide important context for accounts, hosts, IP addresses, URLs, malware, and processes
* The Solorigate incident was mapped to Command and Control
* The disabled account incident involved IP `175.45.176.99`
* The targeted disabled account was `johns@m365x816222.onmicrosoft.com`
* There were `4` login attempts against the disabled account
* Escalation to SOC Level 2 is appropriate when deeper investigation or threat hunting is needed

## Defensive Lessons Learned

This lab reinforced several important defensive lessons:

* Incident ownership keeps investigations accountable
* Incident tasks help standardize SOC workflows
* Status updates help teams understand current response progress
* Log Analytics is critical for validating alert evidence
* Entity analysis helps connect alerts to users, hosts, and infrastructure
* Geolocation enrichment can add useful context to IP based investigations
* Disabled account login attempts should be investigated because they may indicate credential based attacks
* Escalation should include clear context and investigation tasks
* Incident closure should be based on a clear investigation conclusion

## Recommended Defensive Actions

Based on this lab, recommended actions would include:

* Ensure every incident has an assigned owner
* Keep incident status updated during investigation
* Use incident tasks to standardize analyst workflows
* Review alert logs through Link to LA
* Analyze entities before making closure decisions
* Investigate repeated login attempts against disabled accounts
* Alert on suspicious authentication activity
* Escalate incidents when deeper threat hunting is needed
* Use automation rules to reduce known false positives
* Tune analytics rules when alert logic produces inaccurate results
* Document closure classifications clearly
* Review incident handling metrics regularly

## What This Project Demonstrates

This project demonstrates my ability to:

* Work inside Microsoft Sentinel as a SOC analyst
* Triage and manage security incidents
* Take ownership of incidents
* Review alert timelines
* Use Log Analytics for investigation
* Analyze IP and account entities
* Interpret MITRE tactic mapping
* Investigate sign ins against disabled accounts
* Create tasks for deeper threat hunting
* Escalate incidents to higher level analysts
* Apply structured SOC workflows in a cloud security environment

## Disclosure Notice

This writeup is based on an authorized TryHackMe Microsoft Sentinel lab. It is intended to document the investigation process, lab indicators, and defensive concepts learned.

This page does not include private customer data, employer data, production system information, or unauthorized activity.
