# Network Intrusion Detection Lab

## Overview
A hands-on penetration testing lab simulating a realistic network intrusion scenario against a deliberately vulnerable target (Metasploitable 2). The assessment covers the full attack lifecycle — from reconnaissance through exploitation, post-exploitation, and traffic analysis — with all findings documented and mapped to the MITRE ATT&CK framework.

## Lab Environment
| Component | Details |
|-----------|---------|
| Attacker | Kali Linux 2026.1 (192.168.56.102) |
| Target | Metasploitable 2 (192.168.56.101) |
| Network | Isolated VirtualBox Host-Only Network |
| Traffic Capture | Wireshark (eth0) |

## Tools Used
- **Nmap** — Port scanning and service enumeration
- **Metasploit Framework** — Exploitation
- **Netcat** — Bindshell access
- **Wireshark** — Network traffic capture and analysis

## Vulnerabilities Exploited
| Vulnerability | CVE | CVSS | Result |
|--------------|-----|------|--------|
| vsftpd 2.3.4 Backdoor | CVE-2011-2523 | 10.0 | Root shell |
| Samba Username Map Script | CVE-2007-2447 | 10.0 | Root shell |
| Exposed Bindshell (Port 1524) | N/A | 10.0 | Direct root access |

## Key Findings
- Gained root-level access (uid=0) via three separate attack vectors
- Extracted /etc/shadow file exposing system password hashes
- Captured all attack traffic in Wireshark PCAP files
- Identified 7+ additional high-risk services on the target

## MITRE ATT&CK Coverage
| Tactic | Techniques |
|--------|-----------|
| Reconnaissance | T1595.001, T1592, T1590.005 |
| Initial Access | T1190, T1133 |
| Execution | T1059.004 |
| Discovery | T1082, T1087.001 |
| Credential Access | T1003.008 |
| Command & Control | T1095 |

## Deliverables
- [Network Intrusion Detection Lab Report (PDF/DOCX)](./Network_Intrusion_Detection_Lab_Report.docx)
- Screenshots of all exploits and Wireshark captures

## Relevance to Fintech Security
The vulnerabilities demonstrated in this lab mirror real-world risks in fintech environments. Unpatched services, exposed management ports, and weak network segmentation are common findings in financial institution assessments. The detection logic and SIEM queries included in the report can be directly applied to SOC operations monitoring for similar attack patterns.

---
*Conducted in an isolated lab environment for educational and portfolio purposes only.*
