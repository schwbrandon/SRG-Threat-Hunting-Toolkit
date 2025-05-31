# Silent Ransom Group (SRG) Threat Hunting Toolkit

## Overview

This repository provides a curated threat hunting toolkit for the **Silent Ransom Group (SRG)** — also known by aliases such as:

- **Luna Moth** (named by Palo Alto Unit 42)
- **Chatty Spider** (Mandiant Threat Group Naming)
- **UNC3753** (Mandiant UNC Identifier)

SRG has been actively targeting law firms and legal institutions in 2025, leveraging callback phishing, IT helpdesk impersonation, and legitimate remote monitoring and management (RMM) tools for initial access. Their operations focus on stealthy data exfiltration and extortion rather than traditional ransomware encryption.

---

## 🗂️ Repository Structure

- IOCs.txt 
  Verified Indicators of Compromise (IOCs) associated with SRG campaigns in 2025, including:
  - Remote access tool executables
  - Phishing domains and domain patterns
  - Exfiltration tools
  - Hosting providers used for data exfiltration infrastructure

- ThreatHuntingQueries.txt 
  A set of Splunk Search Processing Language (SPL) queries to detect SRG activity based on:
  - Known IOCs
  - Tactics, Techniques, and Procedures (TTPs) such as callback phishing, RMM usage, and data exfiltration.

---

## 🔍 Focus Areas for Detection

- **Phishing Emails**: Callback phishing using spoofed domains and brand impersonation (Duolingo, MasterClass).
- **Remote Access Tool Usage**: Execution of AnyDesk, Zoho Assist, Splashtop, Syncro, AteraAgent, SuperOps.
- **Data Exfiltration**: Use of WinSCP and rclone for stealthy file transfer.
- **Suspicious Domains**: Detection of fake support, invoice, and helpdesk domains.
- **Hosting Providers**: Connections to known VPS infrastructure (Hostwinds, DigitalOcean, Linode).
- **Persistence and Lateral Movement**: Scheduled tasks, new services.
- **Vishing Activity (Voice Phishing)**:  
  SRG heavily relies on voice phishing, convincing victims via phone calls to install remote tools.  
  > **Note**: Many environments do not have detailed telephony logging available. This toolkit focuses on detection via email and endpoint telemetry, which are the most consistently available data sources.

---

## 📝 Reference List

[1] https://www.halcyon.ai/blog/fbi-alerts-on-silent-ransom-group-targeting-law-firms  
[2] https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-071a  
[3] https://www.tanium.com/blog/cti-roundup-luna-moth-venom-spider-stealc-v2/  
[4] https://www.ic3.gov/CSA/2025/250523.pdf  
[5] https://socradar.io/dark-web-profile-silent-ransom-group-leakeddata/  
[6] https://www.hipaajournal.com/silent-ransom-group-law-firm-vishing-attacks/  
[7] https://www.darkreading.com/endpoint-security/fbi-silent-ransom-group-vishing-law-firms  
[8] https://gbhackers.com/luna-moth-hackers-use-fake-helpdesk-domains/  
[9] https://cyberpress.org/luna-moth-fake-helpdesk/  
[10] https://www.bleepingcomputer.com/news/security/luna-moth-extortion-hackers-pose-as-it-help-desks-to-breach-us-firms/  
[11] https://63sats.com/blog/rise-of-luna-moth-how-a-silent-extortion-gang-is-targeting-u-s-law-firms/  
[12] https://www.tanium.com/blog/cti-roundup-luna-moth-venom-spider-stealc-v2/  
[13] https://technijian.com/desktop-support/luna-moth-hackers-masquerade-as-it-helpdesks-to-breach-u-s-firms/  

---

## 📚 Notes

- Only 2025-verified data and sources are reflected in the IOC and threat hunting query lists.
- No 2022-2023 outdated IOCs are included to ensure operational relevance.
- Focused on detection through endpoints and email logs, due to limited telephony data availability in most environments.
- Microsoft Teams, Slack, Zoom, or other collaboration platforms are **not part** of SRG’s known attack vector as of 2025.

---

## 👨‍💻 Contributions

Feel free to open pull requests to add updated IOCs, new hunting queries, or detection techniques as SRG evolves.

---

## 🛡️ Disclaimer

This repository is intended for educational and defensive security purposes. Use responsibly and with proper authorization in your security environments.
