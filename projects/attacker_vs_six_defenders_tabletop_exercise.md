---
layout: project
title: Attacker Vs Six Defenders Tabletop Exercise
---
# Attacker Vs Six Defenders Tabletop Exercise

## Overview

This project documents a tabletop exercise variant developed during my Ascend Learning internship. The exercise was designed to help analysts practice defensive decision making by matching attacker tactics against specific defender counters.

The format placed one attacker against six independent defenders in quick realistic rounds. Each round required the attacker to state a tactic and action, while each defender selected a counter and explained the strongest detection or prevention response.

The goal was to turn security concepts into repeatable analyst practice that improved evidence based thinking, telemetry awareness, and response readiness.

## Project Artifact

[View the Attacker Vs Six Defenders exercise spreadsheet](https://docs.google.com/spreadsheets/d/16gyCWbIm__d8yoxjR4SfqhxMrVD1OvFp/edit?gid=436748229#gid=436748229)

## Scenario Summary

The tabletop exercise used a six defender format where one attacker attempted to move through key phases of an intrusion while defenders responded with detection or prevention actions.

The attacker needed to complete all required gates to win the match. Defenders won a round when at least one defender provided a specific and checkable counter that would stop or detect the attacker action.

The exercise focused on practical security reasoning instead of theory alone.

## Objective

The objective of this project was to:

* Build analyst judgment through repeatable defensive practice
* Help defenders connect attacker tactics to real counters
* Identify which telemetry sources support detection
* Improve team discussion around tools and evidence
* Reveal gaps in detection coverage
* Create a simple scoring model for tabletop exercises
* Support onboarding through safe practice scenarios
* Produce a backlog of defensive improvements

## Key Project Data

| Category | Details |
|---|---|
| Project name | Attacker Vs Six Defenders Tabletop Exercise |
| Associated organization | Ascend Learning |
| Completion date | August 2025 |
| Exercise type | Tabletop incident response and detection exercise |
| Format | One attacker versus six defenders |
| Primary focus | Analyst judgment, detection logic, and response planning |
| Attacker role | A1 |
| Defender roles | D1 to D6 |
| Required gates | Initial Access, Execution, Command and Control, Exfiltration or Impact |
| Scoring model | Attacker win gives 2 points, defender MVP win gives 2 points |
| Business value | Training, detection gap discovery, onboarding, and measurable improvement tracking |

## Exercise Rules

### Roles

The exercise used the following roles:

* Attacker A1
* Defender D1
* Defender D2
* Defender D3
* Defender D4
* Defender D5
* Defender D6

The attacker attempted to move through the attack gates. Each defender independently selected a counter and explained why it would stop or detect the attacker action.

### Round Flow

Each round followed this process:

* The attacker selected a tactic
* The attacker stated a specific action using a card
* Each defender selected a counter card
* Each defender identified their strongest counter
* Defenders could earn an evidence bonus by naming supporting telemetry
* The round was adjudicated based on whether the counter was specific and checkable
* If defenders won, a round MVP was selected

### Evidence Bonus

A defender could earn an evidence bonus by naming:

* One log source
* One tool
* One field check

This helped force defenders to connect their answer to real evidence instead of giving vague responses.

Example evidence thinking:

| Evidence Area | Example |
|---|---|
| Log source | Windows Event Logs, EDR telemetry, firewall logs, DNS logs, proxy logs |
| Tool | SIEM, EDR, email security platform, IDS, case management platform |
| Field check | User, host, process name, destination IP, command line, event ID, timestamp |

### Adjudication

A defender side win occurred when at least one defender gave a specific and checkable counter that would stop or detect the attacker action.

An attacker win occurred when no defender provided a strong enough counter.

The goal was not to reward generic answers. The goal was to reward answers that were tied to real detection, prevention, or investigation evidence.

## Attack Gates

The attacker had to complete all four gates to win the match.

| Gate | Description |
|---|---|
| Initial Access | The attacker attempts to gain entry into the environment |
| Execution | The attacker attempts to run code, commands, or malicious activity |
| Command and Control | The attacker attempts to establish external communication |
| Exfiltration or Impact | The attacker attempts to steal data, disrupt operations, or achieve the final objective |

These gates helped connect the tabletop exercise to common intrusion progression and kill chain thinking.

## Scoring Model

The scoring model was intentionally simple.

| Result | Points |
|---|---:|
| Attacker wins the round | 2 points to attacker |
| Defender side wins the round | 2 points to round MVP defender |
| Non MVP defenders | 0 points |

This made the exercise easy to run while still encouraging defenders to provide strong and specific answers.

## Skills Demonstrated

* Tabletop exercise design
* Incident response planning
* Detection engineering thinking
* Threat modeling
* Kill chain mapping
* Analyst training development
* Evidence based reasoning
* Defensive control mapping
* Detection gap identification
* SOC onboarding support
* Security metrics development
* Cross team communication
* Scenario based learning

## Tools and Concepts Used

* Kill chain concepts
* Initial Access
* Execution
* Command and Control
* Exfiltration
* Impact
* Log source mapping
* SIEM investigation thinking
* EDR detection thinking
* Detection gap analysis
* Security operations training
* Evidence based adjudication
* Analyst skill measurement
* Improvement backlog development

## Exercise Methodology

### 1. Scenario Design

The exercise was designed around fast rounds that forced defenders to think clearly and respond with practical counters.

The goal was to avoid vague answers and require defenders to explain what data source, tool, or field would support their decision.

### 2. Attacker Action Selection

The attacker selected a tactic and specific action from the available cards.

The action needed to align with one of the required gates:

* Initial Access
* Execution
* Command and Control
* Exfiltration or Impact

This gave the attacker a clear path while giving defenders a specific action to counter.

### 3. Defender Counter Selection

Each defender selected a counter card and explained their strongest response.

A strong response needed to be specific, realistic, and checkable.

For example, a strong defender response would not simply say:

* Monitor logs

A stronger response would explain:

* Which log source to check
* Which tool to use
* Which field or event to validate
* How that evidence would detect or stop the action

### 4. Evidence Bonus

The evidence bonus encouraged defenders to support their answer with operational detail.

A strong evidence answer included:

* A log source
* A tool
* A field check

This helped analysts practice thinking like defenders who must prove their findings during real investigations.

### 5. Adjudication

The round was judged based on whether at least one defender provided a specific and checkable counter.

If the defender response could reasonably detect or stop the attacker action, the defender side won.

If the defenders gave vague or unsupported responses, the attacker won.

### 6. Improvement Backlog

The exercise was also designed to reveal detection and process gaps.

When defenders struggled to identify a strong counter, that gap could become an improvement item.

Examples of possible backlog items included:

* Add new detection rule
* Improve logging coverage
* Validate SIEM field mapping
* Update alert triage procedure
* Document response playbook
* Improve analyst onboarding material

## Business Value

This project helped the business by:

* Building analyst judgment through repeatable practice
* Aligning defenders on telemetry, tools, and evidence
* Revealing detection gaps in a safe setting
* Producing a clear improvement backlog
* Supporting faster onboarding for new analysts
* Creating simple metrics leaders could track
* Improving communication between defenders

## Metrics Leaders Could Track

Useful metrics from the exercise included:

| Metric | Why It Matters |
|---|---|
| Gate coverage | Shows whether defenders can respond across the full attack path |
| Time to counter | Measures how quickly defenders identify a response |
| Defender win rate | Shows team readiness against attacker actions |
| Evidence bonus rate | Shows whether answers are tied to real telemetry |
| Detection gap count | Shows where controls or visibility need improvement |
| MVP distribution | Shows which analysts are consistently providing strong counters |

## Key Findings

The exercise demonstrated that:

* Analysts make stronger decisions when forced to name specific evidence
* Defender answers improve when tied to tools and field checks
* Tabletop exercises can reveal gaps without needing a live incident
* Simple scoring keeps the exercise easy to run
* Gate based progression helps connect individual actions to the larger attack path
* Evidence bonuses encourage operational thinking
* The format can support onboarding and continuous improvement

## Defensive Lessons Learned

This project reinforced several important defensive lessons:

* Detection ideas must be tied to real telemetry
* Generic answers are not enough during incident response
* Defenders need to explain how they would prove a finding
* Different defenders may identify different valid counters
* Tabletop exercises are useful for exposing visibility gaps
* Simple rules make training easier to repeat
* Scoring can make practice more engaging without losing the security value

## Recommended Future Improvements

Future improvements to the exercise could include:

* Add more attacker tactic cards
* Add more defender counter cards
* Map each card to MITRE ATT&CK
* Add sample log snippets for each round
* Add difficulty levels for beginner and advanced analysts
* Track time to counter for each defender
* Add a section for detection rule ideas
* Add a section for playbook updates
* Add scoring dashboards for team performance
* Run the exercise regularly with rotating attacker and defender roles

## What This Project Demonstrates

This project demonstrates my ability to:

* Design a practical cybersecurity tabletop exercise
* Connect attacker tactics to defensive actions
* Build a repeatable analyst training format
* Encourage evidence based security reasoning
* Create a simple scoring and adjudication model
* Support SOC training and onboarding
* Identify detection gaps through structured practice
* Translate security concepts into business value
* Communicate how defensive exercises improve readiness

## Disclosure Notice

This project is for education and portfolio demonstration only. All scenarios, datasets, and artifacts are synthetic, publicly available, or redacted to remove sensitive details.

No confidential customer, employer, or production system information is included.
