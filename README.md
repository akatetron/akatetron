# Chayan Panchal — SOC Analyst Portfolio

Hands-on cybersecurity work from HackTheBox Academy and the Google Cybersecurity Professional Certificate, rebuilt here as a single, consistent portfolio for SOC analyst applications.

Every lab folder follows the same structure: a walkthrough PDF explaining what happened and why, a README with the full write-up in plain text, and — wherever the lab provided one — the original source material (pcaps, worksheets, spreadsheets, diagrams) exactly as given. Each folder also has its own accent color, used consistently across its PDFs, so the folders are easy to tell apart at a glance. Where a lab has a graded, single-answer flag or a specific "correct" credential/value, that value is partially masked (first, middle, and last character visible) rather than published in full — enough to confirm the work without handing out answers to a currently-active HTB module.

---

## HackTheBox Academy

Eleven modules covering SOC-analyst-relevant blue team and DFIR work — SIEM triage, threat hunting, incident handling, malware and network traffic analysis, IDS/IPS tuning, and Windows-focused detection engineering. Several of these labs share the same fictional `EAGLE.LOCAL` Active Directory environment and account set (`svc-sql1`, `bonni`), which is why some findings reference each other across folders.

| Folder | What it covers |
|---|---|
| [`security-monitoring-siem-fundamentals`](./htb-academy/security-monitoring-siem-fundamentals) | SIEM data flow, log triage, and a structured escalation decision process |
| [`javascript-deobfuscation`](./htb-academy/javascript-deobfuscation) | Manually deobfuscating malicious JavaScript to recover hidden logic and payloads |
| [`incident-handling-process`](./htb-academy/incident-handling-process) | NIST IH lifecycle, Cyber Kill Chain, Pyramid of Pain, and a full case study investigated in TheHive |
| [`threat-hunting-with-elastic`](./htb-academy/threat-hunting-with-elastic) | Proactive, hypothesis-driven hunting for threats that don't trigger existing alerts |
| [`working-with-ids-ips`](./htb-academy/working-with-ids-ips) | Suricata/Snort rule analysis against real malware families (Empire, Covenant, Sliver, Cerber, Patchwork APT) |
| [`intro-to-network-traffic-analysis`](./htb-academy/intro-to-network-traffic-analysis) | pcap-based network traffic analysis, with original capture files included |
| [`introduction-to-malware-analysis`](./htb-academy/introduction-to-malware-analysis) | Static/behavioral analysis basics — entropy, imphash, exports, registry persistence |
| [`splunk-for-security-analysts`](./htb-academy/splunk-for-security-analysts) | SPL-driven investigation of an LSASS credential-dumping and C2 chain via Sysmon |
| [`windows-attacks-and-defense`](./htb-academy/windows-attacks-and-defense) | AD credential hunting and a full DCSync attack/detection pair |
| [`windows-event-logs-finding-evil`](./htb-academy/windows-event-logs-finding-evil) | Reconstructing a full attack chain (DLL hijack → LSASS dump) from raw Windows Event Logs and Sysmon |
| [`cdsa-capstone-incident-report`](./htb-academy/cdsa-capstone-incident-report) | Original capstone incident report — a full multi-stage intrusion from initial access to domain compromise |

## Google Cybersecurity Professional Certificate

Fifteen shorter, worksheet-style exercises from the "Assets, Threats, and Vulnerabilities" and "Detection and Response" courses — access control, cryptography, Linux permissions, SQL filtering, threat modeling, vulnerability assessment, packet analysis, and incident response fundamentals.

| Folder | What it covers |
|---|---|
| [`access-control`](./google-cybersecurity-certificate/access-control) | Least-privilege incident investigation and a data-leak analysis (NIST SP 800-53 AC-6) |
| [`brute-force-attacks`](./google-cybersecurity-certificate/brute-force-attacks) | Brute force tools and layered defenses (hashing/salting, MFA, CAPTCHA, password policy) |
| [`cryptography`](./google-cybersecurity-certificate/cryptography) | SHA-256 file integrity checks and a Caesar-cipher-into-AES decryption chain |
| [`linux-file-permissions`](./google-cybersecurity-certificate/linux-file-permissions) | Auditing and correcting Linux permissions with `chmod` |
| [`network-hardening`](./google-cybersecurity-certificate/network-hardening) | Core network hardening tasks and attack-surface reduction |
| [`sql-security`](./google-cybersecurity-certificate/sql-security) | Security-focused SQL filtering with AND/OR/NOT/LIKE |
| [`social-engineering`](./google-cybersecurity-certificate/social-engineering) | USB-baiting attack analysis and mitigating controls |
| [`threat-modeling-pasta`](./google-cybersecurity-certificate/threat-modeling-pasta) | Full 7-stage PASTA threat model for a mobile app |
| [`vulnerability-assessment`](./google-cybersecurity-certificate/vulnerability-assessment) | NIST SP 800-30 risk-scored vulnerability assessment of a database server |
| [`wireshark-labs`](./google-cybersecurity-certificate/wireshark-labs) | Wireshark packet filtering and recognizing a SYN flood DoS attack |
| [`tcpdump-labs`](./google-cybersecurity-certificate/tcpdump-labs) | Reading a raw tcpdump log to trace a malware-delivery redirect chain |
| [`incident-response`](./google-cybersecurity-certificate/incident-response) | Three incident reports — SYN flood, ransomware (5 W's), and brute-forced malware delivery |
| [`network-traffic-analysis`](./google-cybersecurity-certificate/network-traffic-analysis) | Diagnosing a DNS outage from ICMP "port unreachable" evidence |
| [`security-audits`](./google-cybersecurity-certificate/security-audits) | Full NIST CSF security audit of a retail company, with a PCI DSS/GDPR/SOC compliance checklist |
| [`risk-management`](./google-cybersecurity-certificate/risk-management) | Bank risk register scored by likelihood x severity, plus a home asset sensitivity inventory |

This repository sits alongside full completion of the Google Cybersecurity Professional Certificate; every graded lab exercise from the program is documented in full above.

## Handwritten study notes

[`handwritten-notes/`](./handwritten-notes) holds personal handwritten notes taken while working through each course of the certificate — kept here for my own reference alongside the polished lab writeups above.

---

## Notes on how this repo is organized

Every module folder follows the same shape: a `README.md` with an overview paragraph and the full walkthrough in prose, one or more PDFs (a `Walkthrough` and, for the larger HTB modules, a companion `Study Notes` PDF with a quick-reference page), and — where the lab provided one — a `source-files/` subfolder with the original worksheets, spreadsheets, diagrams, or packet captures exactly as given. Each folder has its own accent color pair, applied consistently across its own PDFs so the modules are visually distinct from one another while sharing one dark, consistent design system throughout.

---

*Chayan Panchal · [github.com/akatetron](https://github.com/akatetron) · SOC Analyst — Netherlands*
