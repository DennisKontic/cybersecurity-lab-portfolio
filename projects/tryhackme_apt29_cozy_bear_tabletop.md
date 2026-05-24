# APT29 Cozy Bear Tabletop Exercise: Incident Response Simulation

## Overview

This project documents my completion of a TryHackMe tabletop exercise focused on an APT29 Cozy Bear style intrusion. The scenario involved unauthorized access, suspected adversary activity, and data exfiltration concerns.

The exercise tested my ability to apply blue team incident response principles across the full response lifecycle, including detection, triage, containment, eradication, recovery, escalation, and post incident review.

My overall response score was `84/100`, showing strong readiness in containment and escalation while also identifying opportunities to improve detection depth and investigative precision.

## Video Walkthrough

[Watch my APT29 Cozy Bear Tabletop Exercise walkthrough on YouTube](https://www.youtube.com/watch?v=xnOj6vY91uE)

## Scenario Summary

The tabletop exercise simulated a targeted intrusion inspired by APT29 Cozy Bear activity. The scenario required reviewing suspicious activity, classifying alert severity, validating indicators of compromise, making containment decisions, and coordinating response actions.

The exercise focused on:

* Unauthorized access
* Suspicious account activity
* Possible data exfiltration
* Incident triage
* Containment planning
* Escalation workflows
* Recovery planning
* Post incident improvement

## Objective

The objective of this tabletop exercise was to:

* Classify the severity of a suspected intrusion
* Validate indicators of compromise
* Prioritize response actions
* Apply structured incident response principles
* Make containment and eradication decisions
* Support safe recovery of business operations
* Maintain forensic integrity during response
* Escalate to the right stakeholders
* Review response gaps after the incident

## Key Exercise Data

| Category | Details |
|---|---|
| Platform | TryHackMe |
| Exercise | APT29 Cozy Bear Tabletop Exercise |
| Exercise type | Incident response simulation |
| Completion date | October 2025 |
| Associated brand | DonkeySec |
| Overall score | `84/100` |
| Main threat focus | Unauthorized access and data exfiltration |
| Adversary theme | APT29 / Cozy Bear |
| Main skill area | Blue team incident response |
| Primary framework | Incident response lifecycle |
| Core focus | Detection, containment, recovery, and escalation |

## Performance Summary

| Response Area | Score | What It Demonstrated |
|---|---:|---|
| Incident Triage | 100% | Strong ability to classify alert severity, validate indicators, and prioritize response |
| Containment and Eradication | 88% | Strong containment judgment through account isolation and system quarantine decisions |
| Recovery | 75% | Good recovery planning with room to improve restoration depth and validation |
| Escalation | 88% | Strong communication and stakeholder notification decisions |
| Overall Score | 84/100 | Solid readiness across the response lifecycle with room to sharpen detection precision |

## Skills Demonstrated

* Incident triage
* Alert severity classification
* Indicator validation
* Log correlation
* Threat classification
* Adversary behavior analysis
* Data exfiltration response planning
* Containment decision making
* Account isolation planning
* System quarantine planning
* Recovery coordination
* Escalation workflow execution
* Stakeholder communication
* Post incident review

## Frameworks and Concepts Used

* Incident response lifecycle
* Detection and analysis
* Containment
* Eradication
* Recovery
* Escalation
* Lessons learned
* MITRE ATT&CK style thinking
* Threat actor TTP analysis
* Evidence based decision making
* Forensic integrity
* Business impact awareness
* Communication workflows

## Exercise Methodology

### 1. Initial Triage

The exercise began with reviewing suspicious activity and determining whether the alert represented normal behavior, suspicious behavior, or a confirmed incident.

During triage, I focused on:

* Classifying alert severity
* Reviewing available indicators
* Identifying affected users or systems
* Determining whether escalation was needed
* Prioritizing immediate response actions

This was my strongest area in the exercise, with a triage score of `100%`.

### 2. Detection and Analysis

The detection and analysis phase required reviewing available evidence and determining the likely scope of the intrusion.

Key questions included:

* Was the access authorized?
* What indicators supported the alert?
* Were multiple systems or accounts affected?
* Was there evidence of data access or exfiltration?
* Did the activity align with known adversary behavior?
* What response action was most appropriate?

This stage reinforced that early detection decisions must be accurate because they influence every later phase of the response.

### 3. Containment and Eradication

The containment and eradication phase tested my ability to stop the attack from spreading while preserving the ability to investigate.

Actions considered included:

* Isolating affected accounts
* Quarantining affected systems
* Revoking unauthorized access
* Preserving logs and evidence
* Blocking known malicious activity
* Preventing further data exposure

My score in this area was `88%`, showing strong containment judgment.

### 4. Recovery

The recovery phase focused on safely restoring business operations after containment and eradication actions were taken.

Recovery considerations included:

* Confirming that attacker access was removed
* Validating affected accounts and systems
* Restoring normal business operations
* Maintaining forensic integrity
* Monitoring for signs of recurrence
* Ensuring recovery did not reintroduce risk

My score in this area was `75%`, which showed that this is one area where deeper validation and more structured recovery planning could improve future performance.

### 5. Escalation

The escalation phase tested whether the right stakeholders and external parties were notified at the right time.

Escalation considerations included:

* Internal security team notification
* Leadership communication
* Legal or compliance involvement
* Possible external reporting requirements
* Clear incident status updates
* Accurate communication of business impact

My score in this area was `88%`, showing strong communication and escalation decision making.

### 6. Post Incident Review

The final phase focused on reviewing the response and identifying improvements.

This included thinking through:

* What detections worked well
* What evidence needed earlier review
* What response actions were effective
* What communication gaps existed
* What procedures should be updated
* What monitoring should be improved

## Response Lifecycle

| Phase | Response Focus |
|---|---|
| Detection | Identify suspicious activity and validate indicators |
| Analysis | Determine scope, severity, and possible adversary behavior |
| Containment | Limit attacker access and reduce further damage |
| Eradication | Remove unauthorized access and related attacker activity |
| Recovery | Restore safe operations while maintaining forensic integrity |
| Escalation | Notify appropriate stakeholders and coordinate response |
| Lessons Learned | Improve detection, response, and recovery procedures |

## Key Findings

The exercise reinforced that:

* Unauthorized access can quickly become a larger intrusion concern
* Data exfiltration must be investigated early when sensitive information may be involved
* Triage accuracy affects containment and recovery decisions
* Account isolation and system quarantine are important containment options
* Escalation must happen clearly and at the right time
* Recovery should include validation that the threat has been removed
* Incident response requires both technical skill and structured communication

## Defensive Lessons Learned

This tabletop reinforced several important defensive lessons:

* Strong triage helps prevent wasted time during an active incident
* Indicators of compromise must be validated before major response decisions
* Log correlation is critical for understanding scope
* Containment must balance speed with evidence preservation
* Recovery should not be rushed without proper validation
* Escalation workflows should be clear before an incident happens
* Simulations help expose weak points before a real incident occurs

## Recommended Defensive Actions

Based on this exercise, recommended actions would include:

* Improve detection logic for unauthorized access
* Monitor for suspicious authentication activity
* Alert on abnormal data access patterns
* Review potential data exfiltration indicators
* Strengthen account isolation procedures
* Document system quarantine steps clearly
* Preserve logs before major containment actions
* Improve recovery validation checklists
* Review escalation procedures with stakeholders
* Conduct regular tabletop exercises
* Tune detections after simulated incidents
* Practice communication during active response scenarios

## What This Project Demonstrates

This project demonstrates my ability to:

* Apply incident response principles in a tabletop exercise
* Classify alert severity accurately
* Validate indicators of compromise
* Make containment and eradication decisions
* Support recovery planning
* Escalate incidents through proper channels
* Think through adversary behavior and possible objectives
* Use structured communication during an incident
* Identify personal improvement areas after a simulation
* Build readiness for SOC and DFIR work

## Disclosure Notice

This writeup is based on an authorized TryHackMe tabletop exercise. It is intended to document the response process, skills practiced, and defensive concepts learned.

This page does not include private customer data, employer data, production system information, or unauthorized activity.
