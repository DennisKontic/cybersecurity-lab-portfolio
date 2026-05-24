# Deep Blue Investigation: Blue Team Labs Online

## Overview

This project documents my investigation of the Deep Blue lab from Blue Team Labs Online. The scenario involved a compromised Windows workstation where evidence suggested an attack against internet exposed RDP, followed by Meterpreter activity and attacker actions on the host.

The investigation focused on analyzing recovered Windows event logs to confirm malicious activity, identify the affected user, find evidence of Meterpreter behavior, review suspicious service creation, and identify persistence through local account creation.

This lab helped strengthen my Windows event log analysis, DeepBlueCLI usage, process creation review, and incident timeline reconstruction skills.

## Scenario Summary

A Windows workstation was suspected of being compromised through exposed Remote Desktop Protocol access. After gaining access, the attacker appeared to deploy Meterpreter and perform follow on activity.

The provided evidence included:

* Security.evtx
* System.evtx
* Windows process creation events
* Service creation events
* Local account and group modification evidence

The goal was to verify the compromise and identify the attacker activity using the provided logs.

## Objective

The objective of this investigation was to:

* Analyze recovered Windows event logs
* Use DeepBlueCLI to triage suspicious activity
* Identify which user ran a suspicious executable
* Find evidence of Meterpreter activity
* Identify a suspicious service created by the attacker
* Locate the malicious executable used for the reverse shell
* Find evidence of local account creation
* Determine which groups the persistence account was added to
* Reconstruct the attacker timeline

## Key Investigation Data

### Suspicious User Activity

```text
User account that ran GoogleUpdate.exe:
Mike Smith
Suspicious GoogleUpdate Path
C:\Users\Mike Smith\AppData\Local\Google\Update\GoogleUpdate.exe
Meterpreter Activity Time
4/10/2021 10:48:14 AM
Meterpreter Style Command
cmd.exe /c echo rztbzn > \\.\pipe\rztbzn
Suspicious Service Name
rztbzn
Malicious Executable
serviceupdate.exe
Malicious Executable Path
C:\Users\Mike Smith\Downloads\serviceupdate.exe
Persistence Account Created
ServiceAct
Account Creation Command
net user ServiceAct /add
Local Groups Added To
Administrators
Remote Desktop Users
Group Modification Commands
C:\Windows\system32\net1.exe localgroup administrators ServiceAct /add
net localgroup "Remote Desktop Users" ServiceAct /add
Skills Demonstrated
Windows event log analysis
Security.evtx investigation
System.evtx investigation
DeepBlueCLI analysis
Event ID 4688 review
Process creation analysis
Suspicious service detection
Meterpreter behavior identification
RDP compromise investigation
Local account persistence analysis
Privilege escalation evidence review
Timeline reconstruction
Incident documentation
Tools and Evidence Used
DeepBlueCLI
PowerShell
Windows Event Viewer
Security.evtx
System.evtx
Event ID 4688
Event ID 7045
Process creation logs
Service installation logs
Local user and group modification evidence
Investigation Methodology
1. DeepBlueCLI Triage

The investigation began by running DeepBlueCLI against the provided Windows event logs.

The focus was on analyzing the recovered logs, not the live Windows logs from the lab machine.

Example commands:

.\DeepBlue.ps1 .\Security.evtx
.\DeepBlue.ps1 .\System.evtx

DeepBlueCLI helped identify suspicious process creation events and activity that required deeper review.

2. Suspicious Process Review

DeepBlueCLI flagged suspicious activity involving GoogleUpdate.exe.

The suspicious path was:

C:\Users\Mike Smith\AppData\Local\Google\Update\GoogleUpdate.exe

The user account tied to this execution was:

Mike Smith

This was suspicious because attackers often use trusted or legitimate looking process names to hide malicious activity.

3. Meterpreter Activity Identification

DeepBlueCLI identified a command pattern associated with possible Meterpreter activity.

The command was:

cmd.exe /c echo rztbzn > \\.\pipe\rztbzn

This activity occurred at:

4/10/2021 10:48:14 AM

The named pipe behavior was a strong indicator of Meterpreter style activity and helped confirm attacker control after initial compromise.

4. Suspicious Service Creation

The System.evtx log showed suspicious service creation.

The service name was:

rztbzn

This matched the named pipe value observed during the Meterpreter activity, which helped connect the service creation to the attacker activity.

The relevant event type was:

Event ID 7045: Service installed

This finding suggested the attacker created a service to support elevated access or continued control.

5. Event Viewer Review

The investigation continued in Windows Event Viewer by opening the recovered Security.evtx log and filtering for process creation events.

The key event ID was:

4688

The suspicious activity occurred between:

10:30 AM and 10:50 AM on 4/10/2021

During this time window, the malicious executable identified was:

serviceupdate.exe

The path was:

C:\Users\Mike Smith\Downloads\serviceupdate.exe

This executable was tied to the Meterpreter reverse shell activity.

6. Persistence Account Creation

The investigation then focused on activity between:

11:25 AM and 11:40 AM on 4/10/2021

During this time window, a new local account was created.

The command was:

net user ServiceAct /add

The account created was:

ServiceAct

This indicated persistence. The attacker created a new account to maintain future access to the compromised workstation.

7. Local Group Modification

After creating the ServiceAct account, the attacker added it to privileged local groups.

The groups were:

Administrators
Remote Desktop Users

The related commands were:

C:\Windows\system32\net1.exe localgroup administrators ServiceAct /add
net localgroup "Remote Desktop Users" ServiceAct /add

This gave the persistence account administrative privileges and the ability to connect through RDP.

Attack Timeline
Initial Access

The workstation was likely accessed through exposed RDP.

Malicious Payload Execution

The user Mike Smith executed suspicious activity involving:

GoogleUpdate.exe

A malicious executable was also identified:

serviceupdate.exe
Meterpreter Activity

At 4/10/2021 10:48:14 AM, the logs showed Meterpreter style named pipe activity:

cmd.exe /c echo rztbzn > \\.\pipe\rztbzn
Suspicious Service Creation

A suspicious service named rztbzn was created.

Persistence

A new local account was created:

ServiceAct
Privilege Assignment

The attacker added ServiceAct to:

Administrators
Remote Desktop Users
Key Findings

The investigation found that:

The workstation showed evidence of compromise through RDP related activity
Mike Smith was the user account tied to suspicious GoogleUpdate.exe execution
serviceupdate.exe was the malicious executable tied to Meterpreter reverse shell activity
Meterpreter style activity occurred at 4/10/2021 10:48:14 AM
A suspicious service named rztbzn was created
A new local account named ServiceAct was created for persistence
The ServiceAct account was added to Administrators
The ServiceAct account was also added to Remote Desktop Users
The attacker used local account and group changes to maintain access
Defensive Lessons Learned

This lab reinforced several important defensive lessons:

Exposed RDP can become a major initial access risk
Windows event logs can reveal clear attacker behavior after compromise
Event ID 4688 is valuable for process creation analysis
Event ID 7045 is useful for identifying suspicious service installation
DeepBlueCLI can quickly triage Windows event logs
Named pipe activity can help identify Meterpreter behavior
New local account creation should be monitored
Adding accounts to Administrators or Remote Desktop Users should trigger investigation
Suspicious executable names can imitate legitimate software
Timeline reconstruction is critical for understanding attacker actions
Recommended Defensive Actions

Based on the investigation, recommended actions would include:

Disable exposed RDP where possible
Restrict RDP access through VPN or conditional access
Enforce MFA for remote access
Review local administrator group membership
Remove unauthorized local accounts
Disable or remove the ServiceAct account
Investigate and remove suspicious services
Hunt for serviceupdate.exe and related artifacts
Review all process creation logs around the compromise window
Alert on suspicious service creation
Alert on local user creation
Alert on additions to Administrators and Remote Desktop Users
Review firewall logs for RDP source activity
Reimage the host if integrity cannot be trusted
Related Media

Video walkthrough:

https://www.youtube.com/watch?v=_UdxCZ0bO2E
What This Project Demonstrates

This project demonstrates my ability to:

Analyze Windows event logs during a host compromise
Use DeepBlueCLI for rapid event log triage
Identify suspicious process execution
Investigate Meterpreter style activity
Review service creation evidence
Analyze Event ID 4688 process creation logs
Identify persistence through local account creation
Review local group modification activity
Build a timeline from Windows logs
Recommend practical defensive actions
Disclosure Notice

This writeup is based on a retired Blue Team Labs Online training environment. It is intended to document the investigation process, lab indicators, and defensive concepts learned.

This page does not include private customer data, employer data, production system information, or unauthorized activity.
