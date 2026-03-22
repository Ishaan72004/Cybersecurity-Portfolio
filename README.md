# Cybersecurity Portfolio

<!-- Tools & Skills Badges -->
<p align="left">
  <img src="https://img.shields.io/badge/Windows%20Active%20Directory-0078D4?logo=windows&logoColor=white" />
  <img src="https://img.shields.io/badge/Kali%20Linux-557C94?logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Nmap-2C8EBB?logo=nmap&logoColor=white" />
  <img src="https://img.shields.io/badge/BloodHound-CC0000?logo=neo4j&logoColor=white" />
  <img src="https://img.shields.io/badge/Hashcat-EE6C4D?logo=hashcat&logoColor=white" />
  <img src="https://img.shields.io/badge/Shodan-F20000?logo=shodan&logoColor=white" />
  <img src="https://img.shields.io/badge/OSINT-000000?logo=googlescholar&logoColor=white" />
  <img src="https://img.shields.io/badge/Phishing%20Analysis-4B8BBE?logo=gmail&logoColor=white" />
  <img src="https://img.shields.io/badge/Digital%20Forensics-0052CC?logo=icloud&logoColor=white" />
  <img src="https://img.shields.io/badge/Web%20Exploitation-FF6B6B?logo=hackthebox&logoColor=white" />
  <img src="https://img.shields.io/badge/Linux%20Privilege%20Escalation-FCC624?logo=linux&logoColor=black" />
  <img src="https://img.shields.io/badge/Splunk-000000?logo=splunk&logoColor=white" />
  <img src="https://img.shields.io/badge/Threat%20Hunting-CC0000?logo=target&logoColor=white" />
  <img src="https://img.shields.io/badge/MITRE%20ATT%26CK-FF0000?logo=mitre&logoColor=white" />
</p>

A collection of my cybersecurity projects, labs, and research reports covering threat hunting, Active Directory exploitation, web application exploitation, digital forensics, OSINT, and phishing analysis.

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
Investigated a suspected image file → extracted a hidden password-protected ZIP using `binwalk` → cracked the archive password (`159357`) using `fcrackzip` with `rockyou.txt` → decrypted a Caesar cipher flag (ROT21 shift) using CyberChef to reveal `ACESELECTRONS2025{you've_found_it}`.

`binwalk` `fcrackzip` `CyberChef` `Steganography` `Cryptography`
📄 [Digital Forensics & Steganography CTF.pdf](./Blue%20Team/Digital%20Forensics%20%26%20Steganograp....pdf)

---

## 🔴 Red Team

### Active Directory Attack Lab
Built a misconfigured AD lab (Windows Server 2019 + Windows 10) → enumerated DC with `nmap` and `enum4linux` → gained initial access via password spraying (`bob.smith:Password123`) → used BloodHound to discover `GenericAll` DACL misconfiguration → escalated to Domain Admin with `bloodyad` → performed DCSync with `impacket-secretsdump` to dump all hashes including `krbtgt`.

`BloodHound` `crackmapexec` `impacket` `bloodyad` `hashcat` `Kerberos`
📄 [Active Directory Attack Lab.pdf](./Red%20Team/Active%20Directory%20Attack%20Lab.pdf)

---

### Passive Reconnaissance — infosys.com
Full OSINT assessment on `infosys.com` → discovered 845 subdomains and 9 employee emails using `theHarvester`, `Amass`, `Recon-ng` → identified exposed RDP (port 3389) on 2 devices via Shodan → found confidential PDFs indexed by Google via dorking → DNS zone transfer refused (positive security control).

`theHarvester` `Amass` `Recon-ng` `Shodan` `Google Dorking`
📄 [Passive Reconnaissance Report.pdf](./Red%20Team/Passive%20Reconnaissance%20Report....pdf)

---

### DNS Reconnaissance — infosys.com
Passive DNS enumeration on `infosys.com` → mapped A, NS, MX records → discovered 8 active subdomains including ADFS, Salesforce identity, and Microsoft Exchange endpoints → confirmed DNS zone transfer refused by both name servers.

`dnsenum` `dnsrecon` `dnsmap` `dig` `nslookup`
📄 [DNS Reconnaissance Report.pdf](./Red%20Team/DNS%20Reconnaissance%20Report.pdf)

---

### Eloquia — HTB (Web Exploitation — Django / IIS / ExifTool RCE)
Full-stack exploitation on a Windows HTB machine → `nmap` scan revealed HTTP + WinRM → fingerprinted Django backend via `None.JPEG` anomaly and Wappalyzer → identified ExifTool v12.25 (`CVE-2021-22204`) via metadata exposure → exploited DjVu metadata RCE for code execution.

`Nmap` `Burp Suite` `ExifTool` `CVE-2021-22204` `Django` `IIS`
📄 [Eloquia.pdf](./Red%20Team/Eloquia.pdf)

---

### Cap — HTB (IDOR → PCAP Analysis → Credential Harvesting → Linux Privilege Escalation)
Enumerated Linux HTB machine with `nmap` → discovered IDOR on `/data/` endpoint via `ffuf` fuzzing → downloaded historical PCAP and extracted plaintext FTP credentials (`nathan:Buck3th4Tf0RM3!`) in Wireshark → logged in via SSH → escalated to root by abusing `cap_setuid` capability on `python3.8`.

`nmap` `ffuf` `Wireshark` `SSH` `Linux Capabilities` `Python`
📄 [cap.htb.pdf](./Red%20Team/cap.htb.pdf)

---

## 🛠 Skills

| Domain | Skills |
|---|---|
| Threat Hunting | APT Simulation, SIEM Detection, MITRE ATT&CK Mapping |
| Penetration Testing | Active Directory, Web Apps, Windows, Linux |
| Web Exploitation | File Upload, IDOR, RCE via CVE |
| OSINT & Recon | Passive Reconnaissance, DNS Enumeration, Google Dorking |
| Digital Forensics | Steganography, ZIP Cracking, Cryptography |
| Phishing Analysis | Email Header Analysis, SPF/DKIM, IOC Extraction |
| Privilege Escalation | Windows (DACL Abuse, Kerberos) & Linux (Capabilities, SUID) |
| Reporting | Technical Report Writing, Executive Summaries, Remediation Recommendations |
