#Phishing Email Analysis
Project Overview
Phishing is a deceptive technique used to steal sensitive data using digital platforms such as email, SMS, phone calls, and web links. Attackers craft social engineering tactics to trick victims into revealing credentials or downloading malicious content. This project analyzes phishing emails through hands-on methodology, technical tools, and standard procedures.​

Types of Phishing
Information Gathering: Collects user data for future attacks.​

Credential Harvesting: Steals usernames, passwords, and account data.​

Malware Delivery: Disguises malicious files as legitimate attachments.​

Spear Phishing: Targets specific individuals with personalized lures.​

Whaling: Focuses attacks on high-profile victims like executives.​

Vishing: Uses phone calls to collect private information.​

Smishing & Quishing: Employs SMS and QR codes to deceive users.​

Project Workflow
1. Environment Setup
Email Client: Install and configure Thunderbird for email retrieval.​

Text Editor: Install Sublime Text for manual header and content inspection.​

2. Email Header Analysis
Open emails in Sublime Text for raw header review.

Simplify or highlight headers using the 13Cubed tool via Package Control in Sublime Text (Ctrl+Shift+P, search "Email Headers").​

Reference IANA standard email headers for consistency.

IP Verification and WHOIS lookups through Domain Tools for sender legitimacy.​

3. Authentication Methods
SPF (Sender Policy Framework): DNS record validation to authenticate sending servers.​

DKIM (DomainKeys Identified Mail): Public-key encryption for content integrity.​

DMARC (Domain-based Authentication Reporting): Ensures safe mail delivery and reporting.​

Test all headers using MXToolbox Email Header Analyzer.

4. Email Content Analysis
Scan for spelling and grammar mistakes, suspicious MIME versions, and suspicious encodings (content-transfer-encoding, content-type).

Use CyberChef for decoding: Base64, HTML, URL, quoted-printable.​

5. URL Analysis
Defang suspect URLs with CyberChef before investigating.

Verify using PhishTank, url2png, urlscan.io, VirusTotal, Google Transparency Report, and JoeSandbox.

Reference image below for URL anatomy:
<img width="1208" height="470" alt="image" src="https://github.com/user-attachments/assets/de861880-96d4-4a6b-8a5f-d51f462454ed" />


​

6. Attachment Analysis
Download attachments; use hash commands on Ubuntu (sha256sum, sha1sum, md5sum) or PowerShell on Windows (Get-FileHash).​

Use scripts (e.g., eioc.py) for advanced file analysis.

Paste computed hashes into VirusTotal, Cisco Talos, Hybrid Analysis, JoeSandbox, or AnyRun for reputation checking (do not upload sensitive data publicly).

7. IOC (Indicators of Compromise) Extraction
Collect suspicious sender details, URLs, attachment hashes, and other indicators.

Document findings for report generation and threat intelligence sharing.

Practice and Reference Links
PhishTank: Phishing URL repository

VirusTotal: File and URL analysis

Google Transparency Report: URL reputation monitoring

JoeSandbox, AnyRun, Hybrid Analysis: Advanced sandboxing for email analysis

How to Run
Follow steps in "Project Workflow" above for each sample.

Use listed tools and techniques for analysis.

Save observations and IOCs in designated output files for sharing or automation.

Contributing
Feel free to fork the repo, submit pull requests for improvements, or report issues and suggestions via GitHub issues.

License
This project is licensed under MIT License (or select your preferred license).

Acknowledgements
Inspired by:

13Cubed Email Header Tools

CyberChef

IANA Standard Documentation

MXToolbox and VirusTotal

PhishTank Practice URL
