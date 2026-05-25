---
layout: project
title: Countdown Digital Forensics Lab
---
# Digital Forensics Lab: Countdown Investigation

## Overview

This project documents my investigation of the Countdown digital forensics lab from Blue Team Labs Online. The scenario involved a seized laptop connected to a fictional law enforcement investigation. The goal was to analyze digital evidence from the laptop and determine whether a reported threat was real or a hoax.

The investigation focused on disk image analysis, application artifacts, browser history, messaging data, Windows forensic artifacts, and timeline reconstruction.

This project is based on a fictional training scenario. All names, characters, and incidents are fictional and do not represent real events.

## Video Walkthrough

[Watch my Digital Forensics Lab walkthrough on YouTube](https://www.youtube.com/watch?v=D1B6OxxNOCQ)

## Scenario Summary

Law enforcement received information that a group of attackers had entered New York City and may have been planning to detonate an explosive device. Multiple persons of interest were taken into custody, and one additional suspect named `Zerry` was detained during a house raid.

During the search, officers found a laptop, collected the digital evidence, and sent it to the digital forensics division for analysis.

The investigation focused on determining whether the threat was credible by reviewing artifacts from the seized laptop.

## Objective

The objective of this investigation was to:

* Analyze a forensic disk image
* Verify digital evidence integrity
* Review installed applications and execution artifacts
* Analyze messaging application data
* Review browser history
* Identify downloaded or deleted files
* Review Windows thumbnail artifacts
* Analyze SQLite databases
* Review Tor browser artifacts
* Decode hidden or encoded information
* Build a timeline of user activity
* Determine whether the threat was real or a hoax

## Key Investigation Data

| Evidence Type | Finding |
|---|---|
| Lab platform | Blue Team Labs Online |
| Lab name | Countdown |
| Category | Digital Forensics |
| Main evidence | Seized laptop disk image |
| Image format | E01 |
| Suspect name | Zerry |
| Primary forensic tool | Autopsy |
| Supporting tools | Windows File Analyzer, WinPrefetchView, JumpList Explorer, SQLite DB Browser |
| Messaging application reviewed | Signal |
| Browser artifacts reviewed | Chrome and Tor browser artifacts |
| Additional artifacts reviewed | Prefetch, LNK files, thumbcache, Sticky Notes, SQLite databases |
| Encoding clue | ROT13 |
| Main investigation focus | Determine whether a fictional threat was real or a hoax |

## Skills Demonstrated

* Disk image analysis
* Digital evidence review
* Forensic timeline reconstruction
* Autopsy case analysis
* Browser history analysis
* Messaging application artifact review
* SQLite database analysis
* Prefetch review
* Jump List review
* Windows thumbnail cache analysis
* Deleted file artifact review
* OSINT support
* ROT13 decoding
* Forensic reporting

## Tools and Evidence Used

* Autopsy
* Windows File Analyzer
* WinPrefetchView
* JumpList Explorer
* SQLite DB Browser
* FTK Imager report
* E01 disk image
* Signal artifacts
* Chrome History database
* Tor browser history
* Thumbcache database
* Sticky Notes database
* LNK artifacts
* Prefetch artifacts

## Investigation Methodology

### 1. Evidence Verification

The investigation began by reviewing the forensic image and supporting acquisition report.

The goal of this phase was to confirm that the disk image could be trusted before analyzing the contents.

Evidence verification included reviewing:

* Disk image details
* Sector count
* Hash values
* Acquisition information
* Case files and evidence structure

This step helped establish that the investigation was based on a valid forensic image.

### 2. Installed Application Review

Next, I reviewed installed applications and execution artifacts to identify communication tools and suspicious user activity.

Artifacts reviewed included:

* Installed applications
* Prefetch files
* Application execution evidence
* User application activity

This helped identify messaging applications that may have been used for communication.

### 3. Messaging Application Analysis

The investigation found evidence of Signal usage.

Signal artifacts were important because messaging applications can contain conversations, timestamps, contacts, and other evidence that helps build an activity timeline.

The analysis included reviewing:

* Signal configuration files
* Signal database files
* SQLite database content
* Conversation records
* Message bodies
* Contact information
* Timestamps

SQLite DB Browser was used to inspect the database content after the relevant files were exported.

### 4. Browser History Review

Browser history was reviewed to identify web activity connected to the investigation.

The browser artifact review focused on:

* Search activity
* Webmail or messaging access
* Tor browser usage
* Visited websites
* Bookmarks
* Timeline correlation

Browser history helped connect user activity to the broader investigation and provided clues about possible encoding or hidden information.

### 5. Download and File Artifact Review

The investigation included reviewing evidence of downloaded or deleted files.

Artifacts reviewed included:

* Recent document entries
* LNK files
* Download artifacts
* File system metadata
* Application generated artifacts

Even when a file was deleted, Windows artifacts could still show that it existed or had been accessed.

### 6. Thumbnail Cache Review

The thumbnail cache was reviewed to identify visual evidence from files that were no longer directly available.

Thumbnail cache analysis can be useful because Windows may preserve thumbnail previews of images even if the original file is deleted.

This helped support the investigation when the original file was no longer recoverable from the disk image.

### 7. Tor Browser Artifact Review

Tor browser artifacts were reviewed to understand private browsing activity.

The investigation included reviewing:

* Tor browser profile data
* Browser history databases
* Bookmark artifacts
* SQLite browser data

Tor artifacts helped identify a clue related to encoding that became important later in the investigation.

### 8. Sticky Notes and ROT13 Review

The investigation also reviewed Sticky Notes artifacts stored in SQLite database files.

Relevant files included:

```text
plum.sqlite
plum.sqlite-shm
plum.sqlite-wal
```

The Sticky Notes data included encoded content. Based on other artifacts, ROT13 was identified as the likely decoding method.

ROT13 decoding helped reveal hidden information connected to the fictional investigation.

## Investigation Timeline

| Phase | Activity |
|---|---|
| Evidence received | Laptop disk image was provided for forensic analysis |
| Evidence verification | Disk image details and hash information were reviewed |
| Application review | Installed and executed applications were analyzed |
| Messaging review | Signal artifacts were identified and reviewed |
| Browser review | Chrome and Tor browser history were analyzed |
| File review | Downloaded and deleted file artifacts were investigated |
| Thumbnail review | Thumbnail cache was used to recover visual context |
| Notes review | Sticky Notes SQLite files were examined |
| Decoding | ROT13 was used to decode hidden information |
| Conclusion | Evidence was correlated to determine whether the threat was credible |

## Key Findings

The investigation found that:

* The case involved a forensic E01 image from a seized laptop
* Autopsy was used as the primary forensic analysis platform
* Signal artifacts were important to the investigation
* SQLite database analysis helped review messaging and browser artifacts
* Prefetch and application artifacts helped identify executed programs
* Browser history helped reveal user activity and investigative leads
* Tor artifacts provided a clue related to encoding
* Sticky Notes artifacts contained encoded information
* Thumbnail cache analysis helped review image evidence after file deletion
* Timeline correlation was critical to understanding the sequence of activity

## Defensive Lessons Learned

This lab reinforced several important forensic lessons:

* Disk image verification is important before evidence review
* Messaging applications can store valuable forensic artifacts
* SQLite databases are common sources of evidence
* Deleted files can still leave useful traces behind
* LNK files and recent document artifacts can reveal file access
* Thumbnail cache can preserve evidence even when the original file is gone
* Browser history can provide important timeline context
* Tor usage does not eliminate all local forensic artifacts
* Notes applications can contain important user created evidence
* Encoding clues may be found in unrelated artifacts and should be correlated carefully

## Recommended Forensic Actions

Based on this investigation, recommended forensic actions would include:

* Verify disk image integrity before analysis
* Preserve original evidence and work from forensic copies
* Review installed applications and execution artifacts
* Analyze messaging application data carefully
* Export and inspect SQLite databases with proper tooling
* Review browser history across all installed browsers
* Search for LNK and recent document artifacts
* Review thumbnail cache for deleted image evidence
* Examine Sticky Notes and other user note applications
* Correlate timestamps across artifacts
* Document assumptions and findings clearly

## What This Project Demonstrates

This project demonstrates my ability to:

* Analyze a forensic disk image
* Use Autopsy for digital forensic investigation
* Review Windows application artifacts
* Analyze messaging application data
* Inspect SQLite databases
* Review browser and Tor artifacts
* Identify deleted file traces
* Use thumbnail cache artifacts for evidence recovery
* Decode hidden information using ROT13
* Build a forensic timeline
* Communicate findings in a clear investigation report

## Disclaimer

The story, names, characters, and incidents in this lab are fictional. Any similarity to real events is coincidental.

This writeup is based on an authorized Blue Team Labs Online training environment and is intended for education, portfolio demonstration, and defensive security learning.

This page does not include private customer data, employer data, production system information, or unauthorized activity.
