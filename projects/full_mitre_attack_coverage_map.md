---
layout: project
title: Full MITRE ATT&CK Coverage Map
---
# Full MITRE ATT&CK Coverage Map: Ascend Learning

## Overview

This project documents a MITRE ATT&CK coverage mapping project completed during my Ascend Learning security internship.

Ethan and I built a sanitized MITRE ATT&CK coverage map that connected attacker tactics, techniques, and sub techniques to the telemetry collected by Ascend Learning security tools. For each relevant ATT&CK item, we identified supporting log sources and created three detection queries so activity could be captured across three different security tools.

The goal was to turn MITRE ATT&CK from a reference framework into an actionable detection engineering roadmap.

## Project Artifact

[View the sanitized MITRE ATT&CK coverage map](https://docs.google.com/spreadsheets/d/1eaqeuRRDRN7TXyBClfr6SbA37PIwGcj6/edit?gid=105639724#gid=105639724)

## Project Summary

This project helped security analysts and leaders understand where detection coverage was strong, where visibility gaps existed, and what detection improvements should be prioritized next.

The coverage map connected:

* MITRE ATT&CK tactics
* Techniques and sub techniques
* Relevant telemetry sources
* Detection logic
* Security tool coverage
* Coverage gaps
* Future detection improvements

The final result was a practical map that could support monitoring, incident response, threat hunting, and detection engineering decisions.

## Objective

The objective of this project was to:

* Map relevant MITRE ATT&CK tactics and techniques to available telemetry
* Identify which logs could support detection
* Create three detection queries per relevant technique
* Compare visibility across three security tools
* Identify coverage strengths and weaknesses
* Document detection gaps
* Build an actionable improvement roadmap
* Help analysts understand where to investigate suspicious behavior
* Help leaders understand defensive visibility and risk

## Key Project Data

| Category | Details |
|---|---|
| Project name | Full MITRE ATT&CK Coverage Map |
| Associated organization | Ascend Learning |
| Completion period | June 2025 to August 2025 |
| Project type | Detection engineering and coverage analysis |
| Framework | MITRE ATT&CK |
| Primary focus | Mapping attacker behavior to telemetry and detections |
| Detection goal | Three detection queries per relevant technique |
| Tool coverage | Three different security tools |
| Main deliverable | Sanitized ATT&CK coverage spreadsheet |
| Business value | Risk visibility, detection gap tracking, and monitoring improvement |

## Skills Demonstrated

* Detection engineering
* MITRE ATT&CK mapping
* Telemetry analysis
* Detection coverage review
* SIEM query development
* EDR detection thinking
* Threat informed defense
* Security tool comparison
* Gap analysis
* Threat hunting support
* Incident response readiness
* Risk based prioritization
* Technical documentation
* Security reporting

## Tools and Concepts Used

* MITRE ATT&CK
* SIEM telemetry
* EDR telemetry
* Log source mapping
* Detection query development
* Alert logic review
* Coverage scoring
* Gap analysis
* Threat hunting logic
* Incident response use cases
* Tactic and technique mapping
* Detection engineering workflow
* Sanitized reporting

## Coverage Map Structure

The coverage map was designed to make each detection area clear and actionable.

Typical fields included:

| Field | Purpose |
|---|---|
| ATT&CK tactic | Identifies the attacker objective |
| ATT&CK technique | Identifies the specific attacker behavior |
| ATT&CK sub technique | Adds more detail where applicable |
| Telemetry source | Shows what data could support detection |
| Detection query 1 | Query for the first security tool |
| Detection query 2 | Query for the second security tool |
| Detection query 3 | Query for the third security tool |
| Coverage status | Shows whether coverage was strong, partial, or missing |
| Notes | Captures assumptions, gaps, or follow up actions |

## Methodology

### 1. Framework Scoping

The project began by reviewing MITRE ATT&CK tactics, techniques, and sub techniques that were most relevant to the organization’s environment and defensive priorities.

The focus was on mapping realistic attacker behavior to available security data instead of trying to treat the framework as a checklist.

### 2. Telemetry Review

For each relevant technique, we reviewed what telemetry could support detection.

Telemetry review focused on:

* Authentication activity
* Endpoint activity
* Process execution
* Network connections
* Command line behavior
* File activity
* Email related activity
* Cloud or identity activity where applicable
* Security tool events
* Alert data

This step helped determine whether the organization had enough visibility to detect each behavior.

### 3. Detection Query Development

For each relevant tactic, technique, or sub technique, we created three detection queries across the available tools.

The goal was to make the coverage map practical. Instead of only saying a technique was covered, the project documented how that behavior could be searched or detected.

Each query was written to match the available fields, syntax, and telemetry in the tool it was designed for.

### 4. Coverage Comparison

After detection logic was created, we compared coverage across the three tools.

This helped answer questions such as:

* Which tool had the strongest visibility for this behavior?
* Which techniques had coverage in multiple tools?
* Which techniques only had partial coverage?
* Which detections depended on missing or incomplete telemetry?
* Which areas needed future improvement?

### 5. Gap Identification

The map helped identify defensive gaps where detection was limited or missing.

Common gap categories included:

* Missing log source
* Incomplete field visibility
* Tool did not collect the needed telemetry
* Query needed tuning
* Detection logic needed validation
* Coverage existed in one tool but not across others
* Additional enrichment was needed

Each gap could be turned into a future improvement item.

### 6. Roadmap Development

The final output helped create a roadmap for improving detection coverage.

Potential roadmap items included:

* Enable additional logging
* Build new detection rules
* Tune noisy detections
* Validate existing alerts
* Improve field normalization
* Add threat hunting queries
* Document investigation steps
* Improve coverage for high priority ATT&CK techniques

## Detection Engineering Workflow

| Step | Description |
|---|---|
| Select technique | Choose a relevant ATT&CK technique or sub technique |
| Identify telemetry | Determine which logs could show the behavior |
| Build queries | Create detection logic across three tools |
| Review coverage | Determine whether coverage is strong, partial, or missing |
| Document gaps | Capture missing telemetry or weak visibility |
| Prioritize improvements | Turn gaps into actionable work items |
| Support analysts | Give analysts a clearer investigation starting point |

## Example Detection Logic Areas

The project focused on detection logic that could support investigations across common attacker behaviors.

Example behavior areas included:

* Suspicious authentication activity
* Unusual command execution
* Potential credential access behavior
* Lateral movement indicators
* Suspicious network connections
* Endpoint process activity
* Defense evasion behavior
* Command and control indicators
* Data access or exfiltration concerns

Specific internal queries, tool names, field mappings, hostnames, URLs, and proprietary details were sanitized or removed.

## Business Value

This project helped the business by:

* Turning MITRE ATT&CK into an actionable detection roadmap
* Giving analysts a clearer view of available telemetry
* Showing leaders where monitoring coverage was strong
* Identifying gaps that could increase incident response risk
* Creating a structured backlog for detection improvements
* Supporting threat hunting and alert development
* Improving communication between analysts and leadership
* Helping prioritize security work based on attacker behavior

## Key Findings

The project demonstrated that:

* MITRE ATT&CK is most useful when mapped to actual telemetry
* Detection coverage depends heavily on log source quality
* Three tools may show different levels of visibility for the same technique
* Query coverage does not always mean detection coverage is complete
* Field availability and normalization matter during detection engineering
* Coverage maps help analysts and leaders discuss risk using the same language
* Detection gaps should become tracked improvement items

## Defensive Lessons Learned

This project reinforced several important defensive lessons:

* A framework alone does not create coverage
* Detection logic must be tied to available telemetry
* Each tool has different strengths and weaknesses
* Analysts need to know which log sources support each technique
* Gaps should be documented clearly instead of hidden
* Coverage mapping can guide threat hunting and incident response
* Detection engineering should produce work that analysts can actually use

## Recommended Future Improvements

Future improvements could include:

* Validate detection queries with simulated adversary activity
* Add severity and confidence scoring
* Add detection owner fields
* Track query testing status
* Map each detection to response playbooks
* Add false positive notes
* Add data source health checks
* Track coverage changes over time
* Add dashboard views for leadership
* Prioritize gaps based on business risk
* Link coverage gaps to Jira or ServiceNow tickets

## What This Project Demonstrates

This project demonstrates my ability to:

* Build a MITRE ATT&CK coverage map
* Connect attacker behavior to real telemetry
* Develop detection queries across multiple tools
* Identify detection gaps
* Translate technical findings into business value
* Support SOC analysts with actionable detection logic
* Help leadership understand security visibility
* Create a detection improvement roadmap
* Work on professional security projects while protecting confidential information

## Confidentiality Notice

This page describes a sanitized example of professional security work completed during my Ascend Learning internship.

All internal names, hostnames, URLs, tokens, tool specific sensitive details, and proprietary information have been removed or redacted.

No confidential customer, employer, or production system information is included.
