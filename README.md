# Rekall Corporation Penetration Test Report

## Overview

This repository contains a comprehensive penetration test report conducted for Rekall Corporation by Neal LLS (Camron Neal). The goal of this assessment was to evaluate the security posture of Rekall's web applications, Linux and Windows systems, and identify vulnerabilities that could be exploited by attackers.

> **Confidentiality Notice:**  
> This report contains sensitive information and should not be shared publicly or with unauthorized parties. All findings and remediation recommendations are for internal use only.

---

## Assessment Summary

- **Assessment Period:** April 22–28, 2025  
- **Conducted By:** Camron Neal  
- **Organization:** Neal LLS  
- **Client:** Rekall Corporation

---

## Objectives

- Find and exfiltrate sensitive information.
- Escalate privileges across systems.
- Compromise multiple machines within the domain.

---

## Methodology

The following industry-standard phases were executed:

1. **Reconnaissance** – Passive and active data gathering (Nmap, BloodHound).
2. **Vulnerability Identification** – Using tools like Metasploit, Hashcat, Nessus.
3. **Exploitation** – Exploiting found vulnerabilities to gain unauthorized access.
4. **Reporting** – Documenting results and remediation steps.

---

## Key Findings

### ✅ Strengths

- Up-to-date anti-malware solutions.
- Existing defensive countermeasures prevented some attack vectors.

### ❌ Weaknesses

- Cross-Site Scripting (XSS)
- Sensitive data exposure
- Outdated software (Apache Struts)
- Insecure credential storage
- Open ports and FTP vulnerabilities

---

## Vulnerability Summary

| System         | Critical | High | Medium | Low | Informational |
|----------------|----------|------|--------|-----|----------------|
| Web App        | 3        | 3    | 1      | 1   | 0              |
| Linux Server   | 2        | 1    | 1      | 2   | 0              |
| Windows Server | 2        | 1    | 4      | 1   | 0              |

---

## Exploited Tools

- **Metasploit Framework (msfconsole)**
- **Nmap (Standard & Aggressive Scans)**
- **Nessus**
- **John the Ripper**
- **OSINT Framework**
- **Mimikatz (via Kiwi module)**

---

## Notable Exploits

- XSS in `Welcome.php`, `VR Planner.php`, and Comment sections.
- GitHub-stored credentials exposed (`xampp.users`).
- Apache Struts RCE vulnerability.
- Exploited open FTP, SLMail, and task scheduler in Windows systems.
- Extracted NTLM hashes via `lsa_dump_sam`.

---

## Remediation Recommendations

- Sanitize and encode user input to prevent XSS.
- Remove sensitive files and credentials from public GitHub repositories.
- Use SFTP or FTPS instead of plain FTP.
- Patch and update all outdated software (especially Apache Struts).
- Implement IP restrictions, close unused ports (e.g., 110), and monitor open services.
- Enforce least privilege access and secure password/hash storage.

---

## Report History

| Version | Date         | Author       | Description              |
|---------|--------------|--------------|--------------------------|
| 001     | 2025-04-22   | Camron Neal  | Day 1 of CTF Report      |
| 002     | 2025-04-25   | Camron Neal  | Day 2 of CTF Report      |
| 003     | 2025-04-27   | Camron Neal  | Day 3 of CTF Report      |
| 004     | 2025-04-28   | Camron Neal  | Final Draft Submission   |

---

## Contact

**Name:** Camron Neal  
**Title:** Penetration Tester  
**Company:** Neal LLS

---
