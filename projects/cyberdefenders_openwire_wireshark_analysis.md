---
layout: project
title: OpenWire Wireshark Analysis
---
# OpenWire Wireshark Analysis: CyberDefenders

## Overview

This project documents my investigation of the CyberDefenders OpenWire lab. The scenario involved a public facing server that was flagged for making outbound connections to multiple suspicious IP addresses.

The investigation focused on analyzing a packet capture to identify signs of malicious activity, determine the exploited service, identify attacker infrastructure, recover the dropped reverse shell file, and understand how a Java deserialization vulnerability in Apache ActiveMQ was exploited through the OpenWire protocol.

The vulnerability analyzed was `CVE-2023-46604`, a critical Apache ActiveMQ flaw that can allow remote code execution through unsafe handling of serialized Java objects.

## Video Walkthrough

[Watch my OpenWire Wireshark Analysis walkthrough on YouTube](https://www.youtube.com/watch?v=ADD_YOUR_VIDEO_LINK_HERE)

## Scenario Summary

During a shift as a Tier 2 SOC analyst, a Tier 1 analyst escalated activity involving a public facing server. The server was observed making outbound connections to multiple suspicious IP addresses.

The response included isolating the server from the network to limit possible lateral movement or data exfiltration and obtaining a packet capture from the network security monitoring utility.

The goal was to analyze the PCAP and determine whether the server had been exploited.

The investigation focused on:

* Suspicious outbound connections
* OpenWire protocol traffic
* Apache ActiveMQ exposure
* Remote code execution behavior
* Attacker controlled XML delivery
* Reverse shell payload download
* Java class abuse
* CVE identification
* Vendor patch review

## Objective

The objective of this investigation was to:

* Analyze a PCAP for signs of exploitation
* Identify the command and control server
* Determine the exploited service port
* Identify the vulnerable service
* Identify the second C2 server
* Recover the reverse shell executable name
* Identify the Java class invoked by the malicious XML file
* Identify the CVE associated with the vulnerability
* Understand the vendor patch and validation logic
* Translate packet evidence into defensive findings

## Key Investigation Data

| Evidence Type | Finding |
|---|---|
| Lab platform | CyberDefenders |
| Lab name | OpenWire |
| Category | Network Forensics |
| Primary tool | Wireshark |
| Additional tool used | NetworkMiner |
| Vulnerable service | Apache ActiveMQ |
| Protocol | OpenWire |
| Exploited port | `61616` |
| Vulnerability | `CVE-2023-46604` |
| First C2 server | `146.190.21.92` |
| Second C2 server | `128.199.52.72` |
| Reverse shell executable | `docker.elf` |
| Malicious XML file | `invoice.xml` |
| Java class invoked | `java.lang.ProcessBuilder` |
| Vendor fix location | `BaseDataStreamMarshaller.createThrowable` |
| Main risk | Remote code execution |

## Skills Demonstrated

* Network forensics
* PCAP analysis
* Wireshark investigation
* NetworkMiner analysis
* OpenWire protocol review
* Apache ActiveMQ vulnerability analysis
* Command and control identification
* Reverse shell payload identification
* Java deserialization analysis
* CVE research
* Exploit chain reconstruction
* MITRE ATT&CK mapping
* Incident response documentation

## Tools and Evidence Used

* Wireshark
* NetworkMiner
* PCAP evidence
* TCP stream analysis
* HTTP stream analysis
* OpenWire traffic
* Downloaded XML evidence
* Extracted file evidence
* CVE research
* Apache advisory review
* Git commit review
* MITRE ATT&CK

## Investigation Methodology

### 1. PCAP Review

The investigation began by opening the provided packet capture and reviewing the network traffic for suspicious outbound communication.

The scenario indicated that the public facing server had communicated with suspicious IP addresses, so I focused on identifying unusual external connections, protocol usage, and file transfer behavior.

### 2. OpenWire Traffic Analysis

Early in the packet capture, OpenWire traffic was observed. Since OpenWire is used by Apache ActiveMQ, this became an important lead.

The exposed service port identified was:

```text
61616
```

This port aligned with Apache ActiveMQ OpenWire traffic.

### 3. Vulnerable Service Identification

The service found to be vulnerable was:

```text
Apache ActiveMQ
```

This was significant because Apache ActiveMQ was affected by `CVE-2023-46604`, a remote code execution vulnerability involving OpenWire and unsafe Java class handling.

### 4. Command and Control Identification

The first C2 server was identified by following the OpenWire TCP stream and reviewing the suspicious class loading behavior.

The first C2 IP should be added here after confirming it from the PCAP:

```text
ADD_FIRST_C2_IP_FROM_PCAP
```

This IP was associated with the activity where the target server was directed to retrieve malicious XML content.

### 5. HTTP Stream Review

After identifying XML related activity, I reviewed HTTP requests for files ending in `.xml`.

Useful Wireshark filter:

```text
http.request.uri contains ".xml"
```

The malicious XML file identified was:

```text
invoice.xml
```

The XML file contained instructions that caused the server to download and execute a follow on payload.

### 6. Second C2 Server Identification

The second C2 server identified in the investigation was:

```text
128.199.52.72
```

This IP was tied to additional attacker infrastructure used during the payload delivery stage.

### 7. Reverse Shell Payload Identification

Using NetworkMiner and file extraction review, I identified the executable dropped on the server.

The reverse shell executable was:

```text
docker.elf
```

This file was important because it represented the payload used after exploitation to establish attacker control.

### 8. Java Class Review

The malicious XML file invoked a Java class that allowed command execution behavior.

The class identified was:

```text
java.lang.ProcessBuilder
```

Relevant XML style behavior:

```xml
<bean id="pb" class="java.lang.ProcessBuilder" init-method="start">
```

This showed that the XML content was not benign configuration data. It was being used to execute commands on the affected server.

### 9. CVE Identification

The vulnerability associated with the activity was:

```text
CVE-2023-46604
```

This vulnerability affected Apache ActiveMQ and allowed remote code execution through unsafe handling of Java serialized objects in OpenWire.

### 10. Vendor Patch Review

The vendor addressed the vulnerability by adding validation logic to ensure only valid `Throwable` classes could be instantiated.

The Java class and method associated with the validation step was:

```text
BaseDataStreamMarshaller.createThrowable
```

This fix matters because it shows the root issue was not simply that XML was downloaded. The deeper issue involved unsafe object handling that allowed attackers to influence class loading and execution behavior.

## MITRE ATT&CK Mapping

| Tactic | Technique Focus | Evidence |
|---|---|---|
| Initial Access | Exploit Public Facing Application | Public facing Apache ActiveMQ service was exploited |
| Execution | Command execution through Java class abuse | `java.lang.ProcessBuilder` was invoked from malicious XML |
| Command and Control | External attacker infrastructure | Server communicated with suspicious C2 infrastructure |
| Defense Evasion | Use of normal looking filenames | Payload was named `docker.elf` |
| Impact | Potential remote control of server | Reverse shell executable was dropped and executed |

## Attack Timeline

| Phase | Activity |
|---|---|
| Alert escalation | Tier 1 analyst escalated suspicious outbound activity |
| Containment | Server was isolated to limit further risk |
| PCAP review | Network traffic was analyzed for suspicious communication |
| OpenWire discovery | OpenWire traffic was identified on port `61616` |
| Vulnerable service identified | Apache ActiveMQ was confirmed as the exposed service |
| Exploit activity | OpenWire related exploit behavior was observed |
| XML retrieval | Server retrieved `invoice.xml` |
| Command execution | XML invoked `java.lang.ProcessBuilder` |
| Payload download | Reverse shell executable `docker.elf` was dropped |
| Second C2 identified | Additional infrastructure observed at `128.199.52.72` |
| CVE confirmed | Activity mapped to `CVE-2023-46604` |

## Key Findings

The investigation found that:

* The affected server communicated with suspicious external infrastructure
* OpenWire traffic was observed in the packet capture
* The exploited service port was `61616`
* The vulnerable service was Apache ActiveMQ
* The activity was associated with `CVE-2023-46604`
* The malicious XML file was named `invoice.xml`
* The XML file invoked `java.lang.ProcessBuilder`
* The attacker dropped a reverse shell executable named `docker.elf`
* The second C2 server was `128.199.52.72`
* The vendor patch added validation in `BaseDataStreamMarshaller.createThrowable`

## Defensive Lessons Learned

This lab reinforced several important defensive lessons:

* Public facing services must be patched quickly
* OpenWire traffic should be monitored when Apache ActiveMQ is exposed
* PCAP analysis can reveal exploit chains clearly
* TCP and HTTP stream review is critical during network forensics
* XML files retrieved during exploitation should be reviewed carefully
* Reverse shell payloads may use legitimate looking names
* CVE research helps connect observed behavior to known exploitation
* Vendor patch notes can reveal the root cause of a vulnerability
* Isolation is an appropriate early response when outbound C2 activity is suspected

## Recommended Defensive Actions

Based on this investigation, recommended actions would include:

* Patch Apache ActiveMQ to a fixed version
* Restrict public access to ActiveMQ services
* Block suspicious C2 IP addresses
* Block communication with `128.199.52.72`
* Review firewall logs for traffic to port `61616`
* Hunt for `docker.elf` on affected systems
* Review web and proxy logs for `invoice.xml`
* Monitor for suspicious Java process execution
* Alert on unexpected `ProcessBuilder` related execution patterns
* Review EDR telemetry for reverse shell behavior
* Preserve packet captures and system logs for investigation
* Reimage the affected server if integrity cannot be trusted

## What This Project Demonstrates

This project demonstrates my ability to:

* Analyze packet captures during a suspected compromise
* Use Wireshark to investigate suspicious network traffic
* Use NetworkMiner to identify files and hosts
* Identify vulnerable services from network evidence
* Reconstruct an exploitation chain
* Identify reverse shell payload delivery
* Research and map activity to a CVE
* Understand vendor patch details
* Translate network forensic findings into defensive recommendations
* Communicate technical findings in a clean investigation report

## Disclosure Notice

This writeup is based on an authorized CyberDefenders training environment. It is intended to document the investigation process, lab indicators, and defensive concepts learned.

This page does not include private customer data, employer data, production system information, or unauthorized activity.
