# APT34: Zeroed Out by OilRig: TryHackMe Tabletop Exercise

## Overview

This project documents my completion of the TryHackMe tabletop exercise focused on APT34, also known as OilRig. The simulation centered on responding to a targeted intrusion involving unauthorized email access, lateral movement, and attempted goal execution.

The exercise required applying structured incident response decision making across detection and analysis, containment, eradication, recovery, and post incident activity. My final score was `128/150`, which demonstrated solid readiness while also showing areas where I could improve early detection precision and analytical consistency.

## Video Walkthrough

[Watch my APT34 Zeroed Out by OilRig walkthrough on YouTube](https://www.youtube.com/watch?v=-JI80d4KTHw)

## Scenario Summary

The tabletop scenario simulated a targeted intrusion associated with APT34 style activity. The exercise required making incident response decisions as the situation developed, reviewing available evidence, validating suspicious activity, and selecting response actions that would reduce risk to the organization.

The scenario involved:

* Unauthorized email access
* Suspicious account activity
* Possible lateral movement
* Attempted adversary goal execution
* Incident response coordination
* Recovery planning
* Post incident improvement

## Objective

The objective of this tabletop exercise was to:

* Triage suspicious activity quickly
* Validate whether the activity represented a real incident
* Identify adversary behavior and likely objectives
* Apply NIST aligned incident response principles
* Select appropriate containment actions
* Plan eradication and recovery steps
* Communicate clearly during the response process
* Review lessons learned after the incident

## Key Exercise Data

| Category | Details |
|---|---|
| Platform | TryHackMe |
| Exercise | APT34: Zeroed Out by OilRig |
| Exercise type | Tabletop incident response simulation |
| Completion date | November 2025 |
| Associated brand | DonkeySec |
| Final score | `128/150` |
| Main threat focus | Targeted intrusion |
| Adversary theme | APT34 / OilRig |
| Primary activity | Unauthorized email access and lateral movement |
| Response model | NIST aligned incident response |
| Core focus | Detection, containment, recovery, and post incident review |

## Skills Demonstrated

* Incident response decision making
* SOC alert validation
* Suspicious email access review
* Log correlation
* Adversary behavior analysis
* Lateral movement assessment
* Threat actor TTP identification
* Containment planning
* Recovery planning
* Risk based prioritization
* Structured communication
* Post incident improvement

## Frameworks and Concepts Used

* NIST incident response lifecycle
* Detection and analysis
* Containment
* Eradication
* Recovery
* Lessons learned
* MITRE ATT&CK style thinking
* Alert validation
* Incident escalation
* Business impact awareness
* Coordinated response planning

## Exercise Methodology

### 1. Initial Triage

The exercise began with reviewing the initial signs of suspicious activity. The goal was to determine whether the available information suggested normal user behavior, suspicious activity, or a confirmed incident.

During triage, I focused on:

* Validating the alert
* Identifying affected users or assets
* Reviewing suspicious access patterns
* Considering possible attacker objectives
* Prioritizing immediate response actions

### 2. Detection and Analysis

The detection and analysis phase focused on understanding what happened and whether the incident was expanding.

Key questions included:

* Was the email access authorized?
* Did the activity involve unusual login behavior?
* Was there evidence of lateral movement?
* Were additional accounts or systems affected?
* What evidence supported escalation?
* What actions should be taken first?

This stage tested analytical precision and the ability to avoid jumping to conclusions without enough evidence.

### 3. Containment Planning

The containment phase required selecting actions that would limit attacker access while preserving the ability to investigate.

Potential containment considerations included:

* Disabling or restricting compromised accounts
* Revoking active sessions
* Resetting affected credentials
* Preserving logs and evidence
* Limiting lateral movement opportunities
* Coordinating with relevant internal teams

The goal was to contain the threat without causing unnecessary disruption or losing investigation visibility.

### 4. Eradication and Recovery

After containment, the exercise moved into planning how to remove attacker access and restore normal operations.

This required thinking through:

* Removing unauthorized access
* Confirming account security
* Reviewing affected systems
* Validating that persistence was not present
* Restoring business operations safely
* Monitoring for signs of reentry

### 5. Post Incident Activity

The final phase focused on lessons learned and long term improvement.

This included reviewing:

* What detection worked well
* What evidence was missed early
* Which controls should be improved
* How communication could be strengthened
* What procedures should be updated
* What additional monitoring should be added

## Response Lifecycle

| Phase | Response Focus |
|---|---|
| Detection | Identify suspicious email access and related activity |
| Analysis | Validate the incident and determine possible scope |
| Containment | Limit attacker access and reduce spread |
| Eradication | Remove unauthorized access and suspicious activity |
| Recovery | Restore safe operations and monitor for recurrence |
| Lessons Learned | Improve detection, communication, and response procedures |

## Performance Summary

My final score was:

```text
128/150
```

This score showed strong performance in rapid triage, containment decisions, and recovery planning. It also highlighted opportunities to improve precision during the early detection and analysis phase.

The main takeaway was that strong incident response is not only about choosing technical controls. It also requires timing, prioritization, evidence review, and clear communication.

## Key Findings

The exercise reinforced that:

* Unauthorized email access can be an early indicator of a larger intrusion
* Lateral movement must be considered when multiple systems or accounts may be involved
* Early detection decisions affect the entire response timeline
* Containment actions must balance speed with evidence preservation
* Recovery planning should include monitoring for reentry
* Post incident activity is critical for improving future response

## Defensive Lessons Learned

This tabletop reinforced several important defensive lessons:

* Alert validation must happen quickly but carefully
* Email account compromise can lead to broader intrusion activity
* Lateral movement indicators should be reviewed early
* Incident response decisions should follow a structured lifecycle
* Communication matters during every phase of response
* Recovery should not begin until containment and eradication are understood
* Lessons learned should lead to real control improvements

## Recommended Defensive Actions

Based on this exercise, recommended actions would include:

* Monitor for unusual email access activity
* Alert on suspicious authentication patterns
* Review impossible travel and abnormal login behavior
* Enforce MFA for email and remote access
* Revoke active sessions after suspected compromise
* Review mailbox rules and forwarding settings
* Investigate possible lateral movement paths
* Preserve logs before major containment actions
* Improve incident communication templates
* Conduct tabletop exercises regularly
* Review detection logic after each simulated incident

## What This Project Demonstrates

This project demonstrates my ability to:

* Work through a structured incident response scenario
* Apply NIST aligned response principles
* Validate suspicious activity
* Think through adversary behavior
* Identify response priorities
* Make containment and recovery decisions
* Communicate clearly during an incident
* Recognize gaps in early detection precision
* Use tabletop exercises to improve SOC and DFIR readiness

## Disclosure Notice

This writeup is based on an authorized TryHackMe tabletop exercise. It is intended to document the response process, skills practiced, and defensive concepts learned.

This page does not include private customer data, employer data, production system information, or unauthorized activity.
