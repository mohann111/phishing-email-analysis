# Phishing Email Analysis

## Overview

Phishing is a cyberattack technique used to trick users into revealing sensitive data through digital channels such as email, SMS, phone calls, and websites. Attackers employ various social engineering tactics to steal credentials, deliver malware, or obtain private information. This project demonstrates practical analysis of phishing emails using common cybersecurity tools and clearly defined workflows.

***

## Types of Phishing

- **Information Gathering:** Collects user data for future attacks.
- **Credential Harvesting:** Steals usernames, passwords, or other account information.
- **Malware Delivery:** Disguises malicious files as legitimate attachments.
- **Spear Phishing:** Targets specific individuals with tailored messages.
- **Whaling:** Focuses on executives or high-profile individuals.
- **Vishing:** Uses phone calls to obtain information.
- **Smishing & Quishing:** Employs SMS or QR codes for deception.

***

## Project Workflow

### Environment Setup

- **Email Client:** Install and configure Thunderbird for collecting phishing emails.
- **Text Editor:** Install Sublime Text for inspecting email headers and content.

### Email Header Analysis

1. Open emails in Sublime Text to view raw headers.
2. Use the 13Cubed Email Headers package (via Package Control) to highlight and simplify headers.
3. Reference IANA's standard email headers for consistency.
4. Perform sender/IP verification and WHOIS lookups with tools like Domain Tools.

### Authentication Methods

- **SPF (Sender Policy Framework):** Validates sending server via DNS records.
- **DKIM (DomainKeys Identified Mail):** Ensures content integrity with cryptographic signatures.
- **DMARC (Domain-based Authentication Reporting):** Adds policy and reporting for email authentication.
- Analyze all headers using MXToolbox Email Header Analyzer.

### Email Content Analysis

- Review for suspicious spelling/grammar, MIME versions, and encoding fields.
- Use CyberChef to decode/inspect Base64, HTML, URL, and quoted-printable encodings.

### URL Analysis

- Defang suspicious URLs (using CyberChef) before further investigation.
- Check URLs on:
  - PhishTank
  - url2png
  - urlscan.io
  - VirusTotal
  - Google Transparency Report
  - JoeSandbox

#### Example: Anatomy of a URL

<img width="1208" height="470" alt="image" src="https://github.com/user-attachments/assets/87fc13f7-1ad0-47ae-98ef-a21cbe55e729" />


### Attachment Analysis

1. Download suspicious files; use hashing tools on Ubuntu (`sha256sum`, `sha1sum`, `md5sum`) or Windows (`Get-FileHash`).
2. Use scripts (e.g., `eioc.py`) for extracting and analyzing attachments.
3. Submit computed hashes to:
   - VirusTotal
   - Cisco Talos
   - Hybrid Analysis
   - JoeSandbox
   - AnyRun  
   *(Only use public tools for non-sensitive files.)*

### IOC (Indicators of Compromise) Extraction

- Collect sender details, URLs, file hashes, and other relevant indicators.
- Document findings for reporting and threat intelligence.

***

## Practice & References

- **PhishTank:** [Phishing URL repository](https://phishtank.com)
- **VirusTotal:** [File and URL analysis](https://virustotal.com)
- **Google Transparency Report:** [URL reputation monitoring](https://transparencyreport.google.com)
- **JoeSandbox, AnyRun, Hybrid Analysis:** Advanced sandbox environments for attachments

***

## How to Run

1. Follow each step in the Project Workflow above for sample analysis.
2. Apply listed tools and techniques for comprehensive phishing investigations.
3. Document observations and IOCs for reporting.

***

## Contributing

Feel free to fork the repository, submit pull requests with improvements, or open issues for discussion and suggestions.

***


***

## Acknowledgements

- 13Cubed Email Header Tools
- CyberChef
- IANA Standard Documentation
- MXToolbox, VirusTotal, and PhishTank

***
