---
layout: project
title: Real Life Phishing Message Analysis Using ANY.RUN
---

# Analyzing Real Life Phishing Messages Using ANY.RUN

## Overview

This project documents my analysis of real phishing messages that were sent to me. I used ANY.RUN, an interactive online sandbox, to safely inspect suspicious links, understand attacker behavior, and identify the likely objective behind the phishing attempts.

The goal of this project was not only to determine whether the messages were malicious, but also to understand what the attacker wanted, how the lure was structured, what infrastructure was involved, and what defensive lessons could be learned from the activity.

All personal details, private message content, and sensitive information were removed or redacted before documenting this project.

## Video Walkthrough

[Watch my ANY.RUN phishing message analysis walkthrough on YouTube](https://www.youtube.com/watch?v=hntk_0uNXpE)

## Scenario Summary

I received phishing messages that appeared suspicious based on their wording, links, and overall intent. Instead of clicking the links directly on my own device, I used ANY.RUN to safely analyze the URLs inside a controlled sandbox environment.

The investigation focused on understanding:

* Why the message was sent
* What the attacker wanted the victim to do
* Whether the link redirected to suspicious infrastructure
* Whether the page attempted credential theft
* What indicators could be extracted
* How defenders could detect similar activity

## Objective

The objective of this investigation was to:

* Analyze real phishing messages safely
* Use ANY.RUN to inspect suspicious links
* Identify attacker intent
* Review redirect behavior
* Determine whether credential theft was involved
* Extract useful indicators of compromise
* Identify suspicious domains, URLs, or page behavior
* Understand the likely end goal of the threat actor
* Translate findings into defensive recommendations

## Key Investigation Data

| Evidence Type | Finding |
|---|---|
| Project type | Phishing message analysis |
| Tool used | ANY.RUN |
| Message source | Real phishing messages sent to me |
| Primary focus | Suspicious URL analysis |
| Main threat concern | Credential theft or user manipulation |
| Analysis method | Interactive sandbox review |
| Data handling | Personal information redacted |
| Video walkthrough | Available on YouTube |

## Skills Demonstrated

* Phishing analysis
* Suspicious URL investigation
* ANY.RUN sandbox analysis
* Threat actor intent analysis
* Redirect chain review
* Credential theft identification
* Indicator extraction
* Web page behavior analysis
* Browser based threat review
* Defensive reporting
* User awareness analysis
* Incident documentation

## Tools and Evidence Used

* ANY.RUN
* Suspicious phishing messages
* Suspicious URLs
* Redirect behavior
* Web page content
* Network connections
* Domain and URL indicators
* Browser activity inside sandbox
* Screenshot based evidence
* Threat intelligence context

## Investigation Methodology

### 1. Initial Message Review

The investigation began by reviewing the phishing messages for signs of social engineering.

I looked for:

* Suspicious wording
* Urgency
* Requests to click a link
* Unexpected sender behavior
* Login prompts
* Brand impersonation
* Poor grammar or strange formatting
* Mismatched sender and link details
* Attempts to create fear, curiosity, or pressure

This helped determine whether the message was likely designed to manipulate the recipient into taking action.

### 2. URL Collection

The suspicious links were collected from the messages without opening them directly on my own system.

The goal was to avoid exposing my browser, cookies, accounts, or device to a potentially malicious page.

The links were then submitted to ANY.RUN for safe analysis.

### 3. ANY.RUN Sandbox Analysis

ANY.RUN was used to open and inspect the suspicious links in an interactive sandbox environment.

During the sandbox review, I analyzed:

* Page loading behavior
* Redirects
* Domains contacted
* Network connections
* Login forms
* Fake branding
* Page content
* User interaction prompts
* Possible credential harvesting behavior

This allowed me to observe what the phishing link attempted to do without risking my own machine.

### 4. Redirect and Infrastructure Review

A major part of the analysis involved reviewing whether the suspicious link redirected through multiple domains or services.

I looked for:

* Initial URL
* Redirect destination
* Final landing page
* Suspicious domains
* Newly created or unusual domains
* URL parameters
* Tracking values
* Hosting patterns
* Possible phishing kit behavior

Redirect behavior is important because attackers often use multiple stages to hide the final phishing page.

### 5. Credential Theft Review

The investigation focused on whether the landing page attempted to collect sensitive information.

I reviewed whether the page requested:

* Email address
* Password
* MFA code
* Account recovery details
* Personal information
* Payment details
* Session related information

The goal was to determine whether the attacker was attempting credential theft, account takeover, financial fraud, or information collection.

### 6. Threat Actor Intent

After reviewing the messages and sandbox behavior, I analyzed the likely end goal of the attacker.

Possible attacker goals included:

* Stealing account credentials
* Capturing MFA codes
* Taking over email or social media accounts
* Redirecting victims to fake login portals
* Collecting personal information
* Delivering malware
* Preparing for follow up fraud
* Using stolen access for additional phishing

This helped connect the technical evidence to the attacker’s motivation.

### 7. Indicator Extraction

Useful indicators were collected from the sandbox session.

Potential indicators included:

* Suspicious URLs
* Domains
* Redirect links
* IP addresses
* Page titles
* Network requests
* Brand impersonation details
* Login form behavior
* Phishing kit patterns

These indicators could be used for blocking, alerting, or further research.

## Attack Timeline

| Phase | Activity |
|---|---|
| Message delivery | Phishing message was sent to the recipient |
| Social engineering | Message attempted to pressure or convince the user to click |
| Link interaction | Suspicious URL was submitted to ANY.RUN instead of opened locally |
| Redirect review | Sandbox showed the link path and final destination |
| Landing page review | Suspicious page content and possible fake login behavior were analyzed |
| Intent analysis | Attacker goal was assessed based on message and page behavior |
| Indicator extraction | Suspicious URLs, domains, and behavior were documented |
| Defensive reporting | Findings were translated into user awareness and detection recommendations |

## Key Findings

The investigation found that:

* The messages showed characteristics of phishing
* ANY.RUN provided a safe way to analyze suspicious links
* The suspicious URLs could be reviewed without exposing my own browser
* Redirect behavior was important for understanding the attack path
* The attacker likely wanted the victim to interact with a fake or suspicious page
* The likely goal was credential theft, account takeover, or further fraud
* Sandbox behavior helped reveal infrastructure and page activity
* Real phishing messages are useful for practicing practical analysis skills

## Defensive Lessons Learned

This project reinforced several important defensive lessons:

* Suspicious links should not be opened directly on a personal or work device
* ANY.RUN is useful for safely reviewing phishing links
* Phishing messages often rely on urgency, trust, or curiosity
* Redirect chains can hide the final phishing destination
* Fake login pages are a common method for credential theft
* Indicators should be collected carefully for blocking and detection
* User awareness matters because phishing depends on interaction
* Analysts should focus on both technical evidence and attacker intent

## Recommended Defensive Actions

Based on this investigation, recommended actions would include:

* Avoid opening suspicious links directly
* Submit suspicious URLs to a sandbox or safe analysis platform
* Block confirmed malicious domains and URLs
* Report phishing messages to the email security team or platform provider
* Review email gateway logs for similar messages
* Search for other users who received the same message
* Reset credentials if a user interacted with the phishing page
* Revoke active sessions if account compromise is suspected
* Enable MFA on important accounts
* Train users to recognize urgency based phishing lures
* Create detections for repeated phishing infrastructure
* Document indicators for future threat hunting

## What This Project Demonstrates

This project demonstrates my ability to:

* Analyze real phishing messages safely
* Use ANY.RUN for suspicious URL analysis
* Identify social engineering tactics
* Review redirect behavior
* Understand attacker intent
* Extract useful indicators
* Recognize credential theft patterns
* Translate phishing findings into defensive actions
* Communicate practical lessons for users and defenders

## Disclosure Notice

This writeup is based on real phishing messages sent to me and analyzed in a safe sandbox environment.

Personal information, private message content, email addresses, account details, and sensitive artifacts have been removed or redacted.

This project is intended for education, portfolio demonstration, and defensive security awareness.
