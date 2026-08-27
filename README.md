# Cybersecurity Portfolio

<!-- Tools & Skills Badges -->
<p align="left">
  <img src="https://img.shields.io/badge/Windows%20Active%20Directory-0078D4?logo=windows&logoColor=white" />
  <img src="https://img.shields.io/badge/Kali%20Linux-557C94?logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Nmap-2C8EBB?logo=nmap&logoColor=white" />
  <img src="https://img.shields.io/badge/BloodHound-CC0000?logo=neo4j&logoColor=white" />
  <img src="https://img.shields.io/badge/Hashcat-EE6C4D?logoColor=white" />
  <img src="https://img.shields.io/badge/Phishing%20Analysis-4B8BBE?logoColor=white" />
  <img src="https://img.shields.io/badge/Digital%20Forensics-0052CC?logoColor=white" />
  <img src="https://img.shields.io/badge/Web%20Exploitation-FF6B6B?logoColor=white" />
  <img src="https://img.shields.io/badge/Linux%20Privilege%20Escalation-FCC624?logo=linux&logoColor=black" />
  <img src="https://img.shields.io/badge/Splunk-000000?logo=splunk&logoColor=white" />
  <img src="https://img.shields.io/badge/Threat%20Hunting-CC0000?logoColor=white" />
  <img src="https://img.shields.io/badge/MITRE%20ATT%26CK-FF0000?logoColor=white" />
  <img src="https://img.shields.io/badge/AWS-232F3E?logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/Microsoft%20Entra%20ID-0078D4?logo=microsoft&logoColor=white" />
  <img src="https://img.shields.io/badge/pfSense-212121?logoColor=white" />
  <img src="https://img.shields.io/badge/NIST%20CSF-003B5C?logoColor=white" />
  <img src="https://img.shields.io/badge/CIS%20Controls-005A9C?logoColor=white" />
  <img src="https://img.shields.io/badge/OSINT-555555?logoColor=white" />
</p>

A collection of my cybersecurity projects, labs, security assessments, and research reports covering threat hunting, Active Directory exploitation, web application exploitation, digital forensics, phishing analysis, network security, cloud security, IAM/PAM, and OSINT investigation.

---

## 🔵 Blue Team

### APT41 Threat Hunt — TTP Simulation & Detection
Simulated 6 APT41 (Double Dragon) TTPs using Atomic Red Team on a Windows 10 lab → detected malicious service installation (`AtomicTestService`), privilege abuse via `SeDebugPrivilege` (348 events), and backdoor account creation via SYSTEM → identified 3 logging gaps with remediation recommendations using Splunk SIEM.

`Splunk` `MITRE ATT&CK` `Atomic Red Team` `Windows Event Logs`  
📄 [APT41_Threat_Hunt_Report.pdf](./Blue%20Team/APT41_Threat_Hunt_Report.pdf)

---

### Phishing Analysis — Live Microsoft Credential Theft Campaign
Analyzed a real-world phishing email (`sample-1011.eml`) impersonating Microsoft → dissected email headers revealing SPF/DKIM authentication failures and sender spoofing from `nonkfrgr.co.uk` → extracted payload URL using `grep` → confirmed malicious via VirusTotal (8/90 vendors flagged as Phishing/Malware).

`Email Header Analysis` `VirusTotal` `SPF/DKIM` `Social Engineering`  
📄 [Phishing Analysis Research.pdf](./Blue%20Team/Phishing%20Analysis%20Research.pdf)

---

### Digital Forensics & Steganography CTF
Investigated a suspected image file → extracted a hidden password-protected ZIP using `binwalk` → cracked the archive password using `fcrackzip` with `rockyou.txt` → decrypted a Caesar cipher flag (ROT21 shift) using CyberChef.

`binwalk` `fcrackzip` `CyberChef` `Steganography` `Cryptography`  
📄 [Digital Forensics & Steganography CTF.pdf](./Blue%20Team/Digital%20Forensics%20%26%20Steganography%20CTF.pdf)

---

### Network Security Assessment — Enterprise Firewall & Segmentation
Performed an enterprise-style network security assessment using pfSense → assessed WAN/LAN/DMZ segmentation, firewall policies, management-plane exposure, DMZ-to-LAN isolation, SMB/lateral-movement exposure, and firewall logging → identified a management-interface exposure from the DMZ → implemented remediation and validated the fix through retesting.

`pfSense` `Firewall` `DMZ` `Network Segmentation` `Nmap` `Wireshark`  
📄 [Network Security Assessment.pdf](./Blue%20Team/Network_Security_Assessment.pdf)

---

### Internship Fraud Investigation — OSINT Case Study
Conducted an OSINT investigation into an online internship operation → analyzed website configuration, domain information, company records, listed addresses, LinkedIn presence, application workflow, LMS access, and enrollment requirements → documented 26 pieces of evidence across the investigation → identified multiple fraud indicators and produced a consolidated risk assessment.

`OSINT` `WHOIS` `MCA Verification` `LinkedIn Investigation` `Evidence Analysis` `Fraud Investigation`  
📄 [Internship Fraud Investigation.pdf](./Blue%20Team/Internship_Fraud_Investigation.pdf)

---

## ☁️ Cloud Security & IAM-PAM

### AWS Cloud Security Assessment
Performed an AWS security configuration assessment → reviewed IAM, root-account security, MFA, S3, CloudTrail, IAM Access Analyzer, VPC, EC2 security groups, KMS, logging, and monitoring → identified security configuration gaps and documented risk-rated findings with remediation recommendations.

`AWS` `IAM` `S3` `CloudTrail` `VPC` `EC2` `KMS` `Security Assessment`  
📄 [AWS Security Assessment.pdf](./Cloud-Security-IAM-PAM/AWS_Security_Assessment.pdf)

---

### Microsoft Entra IAM & PAM Security Lab
Built an identity-security lab using Microsoft Entra ID → demonstrated RBAC and least privilege through Security Reader assignment → investigated MFA, authentication methods, sign-in activity, and audit logs → evaluated privileged access and PIM/JIT access concepts while documenting platform limitations.

`Microsoft Entra ID` `IAM` `RBAC` `MFA` `PAM` `PIM` `Least Privilege`  
📄 [Microsoft Entra IAM PAM Security.pdf](./Cloud-Security-IAM-PAM/Microsoft_Entra_IAM_PAM_Security.pdf)

---

## 🔴 Red Team

### Active Directory Attack Lab
Built a misconfigured AD lab (Windows Server 2019 + Windows 10) → enumerated DC with `nmap` and `enum4linux` → gained initial access via password spraying → used BloodHound to discover `GenericAll` DACL misconfiguration → escalated to Domain Admin with `bloodyad` → performed DCSync with `impacket-secretsdump` to demonstrate domain credential exposure.

`BloodHound` `crackmapexec` `impacket` `bloodyad` `hashcat` `Kerberos`  
📄 [Active Directory Attack Lab.pdf](./Red%20Team/Active%20Directory%20Attack%20Lab.pdf)

---

### Eloquia — HTB (Web Exploitation — Django / IIS / ExifTool RCE)
Full-stack exploitation on a Windows HTB machine → `nmap` scan revealed HTTP + WinRM → fingerprinted Django backend via `None.JPEG` anomaly and Wappalyzer → identified ExifTool v12.25 (`CVE-2021-22204`) via metadata exposure → exploited DjVu metadata RCE for code execution.

`Nmap` `Burp Suite` `ExifTool` `CVE-2021-22204` `Django` `IIS`  
📄 [Eloquia.pdf](./Red%20Team/Eloquia.pdf)

---

### Cap — HTB (IDOR → PCAP Analysis → Credential Harvesting → Linux Privilege Escalation)
Enumerated Linux HTB machine with `nmap` → discovered IDOR on `/data/` endpoint via `ffuf` fuzzing → downloaded historical PCAP and extracted plaintext FTP credentials in Wireshark → logged in via SSH → escalated to root by abusing `cap_setuid` capability on `python3.8`.

`nmap` `ffuf` `Wireshark` `SSH` `Linux Capabilities` `Python`  
📄 [cap.htb.pdf](./Red%20Team/cap.htb.pdf)

---

## 🛠 Skills

| Domain | Skills |
|---|---|
| Security Operations | SOC Monitoring, Alert Triage, Incident Investigation, Threat Hunting |
| SIEM & Detection | Splunk, ELK Stack, Microsoft Sentinel, KQL, Windows Event Logs |
| Threat Hunting | APT Simulation, SIEM Detection, MITRE ATT&CK Mapping, IOC Analysis |
| Network Security | pfSense, Firewalls, DMZ, Network Segmentation, Wireshark, Nmap |
| Cloud Security | AWS, IAM, S3, CloudTrail, VPC, EC2, KMS |
| Identity & Access | Microsoft Entra ID, Active Directory, RBAC, MFA, PAM, PIM, Least Privilege |
| Penetration Testing | Active Directory, Web Apps, Windows, Linux |
| Web Exploitation | File Upload, IDOR, RCE via CVE |
| Digital Forensics | Steganography, ZIP Analysis, Cryptography, PCAP Analysis |
| Phishing Analysis | Email Header Analysis, SPF/DKIM, IOC Extraction, Social Engineering |
| OSINT | WHOIS, MCA Verification, Website Analysis, LinkedIn Investigation, Evidence Correlation |
| Privilege Escalation | Windows (DACL Abuse, Kerberos) & Linux (Capabilities) |
| Security Assessment | Configuration Review, Control Validation, Risk Assessment, Remediation |
| Frameworks | NIST Cybersecurity Framework, CIS Controls, MITRE ATT&CK |
| Reporting | Technical Report Writing, Executive Summaries, Remediation Recommendations |

---

## 📋 Security Assessment Methodology

My assessment work follows a structured approach:

`Scope` → `Asset Identification` → `Configuration Review` → `Control Validation` → `Finding Identification` → `Risk Assessment` → `Remediation` → `Retesting` → `Reporting`

### Frameworks

`NIST Cybersecurity Framework (CSF)` `CIS Controls` `MITRE ATT&CK`

---

## 📄 Documentation

Security assessment and investigation reports include:

- Scope and objectives
- Methodology
- Technical findings
- Supporting evidence
- Risk and impact
- Remediation recommendations
- Validation / retesting where applicable
- Final assessment conclusions

---

## 📫 Contact

**Ishaan Malhotra**

Cybersecurity | Security Operations | Security Assessments | Cloud & IAM | Network Security

- GitHub: [Ishaan72004](https://github.com/Ishaan72004)
- Email: malhotra.ishaan04@gmail.com

---

> All security testing and exploitation activities are performed in authorized laboratory environments or against publicly available information.
