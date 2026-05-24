# UNC3944 Scattered Spider Tabletop Exercise: TryHackMe

## Overview

This project documents my completion of the TryHackMe UNC3944 Scattered Spider tabletop exercise. The scenario simulated a data theft incident targeting a telecommunications company and required coordinated incident response decision making across IT and security teams.

The exercise tested my ability to triage alerts, investigate possible administrator misuse, review suspicious activity across Linux and Mac systems, and coordinate containment and recovery actions in a cloud based environment.

I successfully responded to multiple injects covering initial access, lateral movement, and execution phases. My ratings ranged from moderate to most effective, showing solid incident response judgment while also identifying areas for continued improvement.

## Video Walkthrough

[Watch my UNC3944 Scattered Spider tabletop walkthrough on YouTube](https://www.youtube.com/watch?v=TXjUkoiGQj4)

## Scenario Summary

The tabletop exercise simulated a security incident involving a telecommunications company. The organization was facing a possible data theft event where suspicious administrator behavior, cloud activity, and endpoint evidence needed to be investigated.

The scenario involved:

* Alert triage
* Suspected administrator misuse
* Cloud based activity
* Linux system evidence
* Mac system evidence
* Initial access activity
* Lateral movement concerns
* Execution related activity
* Containment decisions
* Recovery planning
* Coordination between IT and security teams

## Objective

The objective of this tabletop exercise was to:

* Triage suspicious alerts quickly
* Determine whether administrator activity was legitimate or malicious
* Investigate possible data theft behavior
* Review cloud based evidence
* Evaluate activity across Linux and Mac systems
* Respond to injects across different stages of the attack
* Coordinate containment actions with IT and security teams
* Plan recovery steps while preserving operational stability
* Communicate decisions clearly during an active incident

## Key Exercise Data

| Category | Details |
|---|---|
| Platform | TryHackMe |
| Exercise | UNC3944 Scattered Spider |
| Exercise type | Tabletop incident response simulation |
| Completion date | October 2025 |
| Associated brand | DonkeySec |
| Main threat focus | Data theft incident |
| Target environment | Telecommunications company |
| Environment focus | Cloud, Linux, and Mac systems |
| Key concern | Administrator misuse |
| Attack phases covered | Initial access, lateral movement, execution |
| Performance range | Moderate to most effective |
| Core focus | Triage, containment, recovery, communication, and escalation |

## Skills Demonstrated

* Incident response decision making
* Alert triage
* Administrator misuse investigation
* Cloud security investigation
* Linux activity review
* Mac activity review
* Data theft response planning
* Lateral movement assessment
* Execution phase analysis
* Containment planning
* Recovery coordination
* Escalation judgment
* Cross team communication
* Business impact awareness

## Frameworks and Concepts Used

* Incident response lifecycle
* Detection and analysis
* Containment
* Eradication
* Recovery
* Escalation
* Lessons learned
* MITRE ATT&CK style thinking
* Cloud incident response
* Identity and access review
* Endpoint investigation
* Evidence based decision making
* Stakeholder communication

## Exercise Methodology

### 1. Initial Triage

The exercise began with reviewing the initial alert information and determining whether the activity required escalation.

During triage, I focused on:

* Identifying the alert source
* Determining affected users and systems
* Reviewing whether administrator actions were expected
* Prioritizing the most urgent risks
* Deciding which evidence needed immediate review
* Determining whether the incident involved possible data theft

The main goal was to quickly separate normal administrative behavior from activity that could indicate attacker control or misuse.

### 2. Administrator Misuse Investigation

A major part of the exercise involved investigating suspicious administrator activity.

I focused on questions such as:

* Was the administrator activity authorized?
* Did the activity occur during expected business hours?
* Was the source location or access pattern unusual?
* Were privileged actions performed against sensitive systems?
* Was there evidence of account misuse or compromise?
* Did the activity support possible lateral movement or data theft?

This helped reinforce the importance of reviewing privileged account activity carefully during incident response.

### 3. Cloud Based Activity Review

The scenario included a cloud based environment, which required thinking beyond traditional endpoint investigation.

Cloud investigation considerations included:

* Account activity
* Privileged access
* Resource access
* Suspicious authentication
* Possible data access
* Evidence of unauthorized changes
* Coordination between cloud logs and endpoint activity

This strengthened my understanding of how cloud based investigations rely heavily on identity, access, and activity logs.

### 4. Linux and Mac System Review

The exercise also involved Linux and Mac systems, which required considering different types of evidence and response actions.

The investigation focused on:

* Suspicious user behavior
* Possible execution activity
* Unusual access patterns
* Endpoint activity tied to the incident
* Whether systems needed containment
* How evidence should be preserved before recovery

This helped reinforce that modern SOC and DFIR work often involves mixed operating system environments.

### 5. Inject Response

The tabletop presented multiple injects across the simulated incident. Each inject required selecting a response action based on the available evidence.

The injects covered activity related to:

* Initial access
* Lateral movement
* Execution
* Suspicious administrator behavior
* Data theft concerns
* Containment and recovery decisions
* Communication between teams

My responses earned ratings from moderate to most effective, showing that I was able to make practical response decisions under changing conditions.

### 6. Containment and Recovery Planning

The containment phase focused on limiting attacker access and stopping further impact.

Containment considerations included:

* Restricting suspicious administrator access
* Isolating affected systems when needed
* Preserving logs and evidence
* Coordinating actions with IT
* Avoiding unnecessary disruption
* Preventing additional data exposure

Recovery planning focused on restoring normal operations safely while continuing to monitor for signs of continued compromise.

### 7. Communication and Escalation

The exercise required clear communication between IT and security teams.

Communication priorities included:

* Explaining what was known
* Identifying what still needed investigation
* Escalating high risk activity
* Coordinating containment actions
* Keeping business impact in mind
* Documenting decisions clearly

This reinforced that incident response is not only technical. It also depends on clear coordination and timely communication.

## Response Lifecycle

| Phase | Response Focus |
|---|---|
| Detection | Review alerts and identify suspicious administrator activity |
| Analysis | Validate whether the activity represented compromise or misuse |
| Containment | Limit attacker access and reduce the risk of data theft |
| Eradication | Remove unauthorized access and address affected systems |
| Recovery | Restore operations safely and continue monitoring |
| Communication | Coordinate across IT, security, and stakeholders |
| Lessons Learned | Identify improvements for detection, process, and response |

## Key Findings

The exercise reinforced that:

* Administrator misuse can be difficult to distinguish from normal activity
* Cloud based incidents require strong identity and access visibility
* Data theft investigations require fast evidence preservation
* Linux and Mac systems must be included in response planning
* Lateral movement concerns should be reviewed early
* Containment actions must be coordinated across IT and security teams
* Communication quality affects the success of the response
* Tabletop simulations help expose process gaps before a real incident occurs

## Defensive Lessons Learned

This tabletop reinforced several important defensive lessons:

* Privileged account activity should be monitored closely
* Suspicious administrator behavior should trigger rapid investigation
* Cloud logs are critical during data theft investigations
* Mixed Linux and Mac environments require broad investigation skills
* Lateral movement indicators should be reviewed early
* Containment should preserve evidence where possible
* Recovery should include continued monitoring for reentry
* Incident response requires both technical accuracy and clear communication

## Recommended Defensive Actions

Based on this exercise, recommended actions would include:

* Monitor privileged administrator activity
* Alert on unusual administrator login behavior
* Review cloud identity and access logs
* Investigate suspicious activity across Linux and Mac systems
* Preserve logs before major containment actions
* Restrict or suspend suspicious privileged accounts
* Review access to sensitive data repositories
* Improve data theft detection logic
* Coordinate containment actions with IT operations
* Document escalation paths before an incident
* Run recurring tabletop exercises for security and IT teams
* Review response quality after each simulation

## What This Project Demonstrates

This project demonstrates my ability to:

* Respond to a simulated data theft incident
* Triage alerts in a tabletop environment
* Investigate suspicious administrator activity
* Think through cloud based incident response
* Consider Linux and Mac evidence during investigation
* Respond to injects across initial access, lateral movement, and execution
* Coordinate containment and recovery actions
* Communicate clearly across IT and security teams
* Apply structured incident response thinking
* Build readiness for SOC and DFIR work

## Disclosure Notice

This writeup is based on an authorized TryHackMe tabletop exercise. It is intended to document the response process, skills practiced, and defensive concepts learned.

This page does not include private customer data, employer data, production system information, or unauthorized activity.
