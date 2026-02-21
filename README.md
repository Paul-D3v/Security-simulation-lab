# Security Simulation Lab — BINCOM Academy Cybersecurity Practical Test

**Student:** Paul Umeh Ogonna  
**Date:** January 27–28, 2026  
**Environment:** Isolated VMware Lab Network (192.168.2.0/24)

---

## Overview

This project documents a full cybersecurity simulation conducted as part of the BINCOM Academy Cybersecurity Practical Test. The exercise covered both offensive and defensive security — deploying vulnerable systems, executing real attacks, and monitoring everything using industry-standard tools.

**End result: 21,646 attack events logged with a 100% detection rate.**

---

## Network Architecture

![Network Diagram](Network_diagram.png).

| System | IP Address | Role |
|--------|-----------|------|
| Kali Linux 2023 | 192.168.2.1 | Attacker Machine |
| Ubuntu Server 22.04 | 192.168.2.142 | Target + Defender |

---

## What Was Deployed

**Target Side:**
- DVWA (Damn Vulnerable Web Application) running on Apache 2.4.52
- Cowrie SSH Honeypot on port 2222
- ModSecurity WAF v2.9.5
- ELK Stack (Elasticsearch 8.19.10, Logstash, Kibana) for real-time monitoring

**Attacker Side:**
- Nmap 7.94 — Network discovery and port scanning
- Nikto 2.5.0 — Web vulnerability scanning
- Hydra 9.6 — Brute force attacks
- SQLMap — SQL injection testing

---

## Attacks Executed

**Phase 1 — Reconnaissance**
- Full port scan across 65,535 ports
- Service version detection and OS fingerprinting

**Phase 2 — Scanning**
- Nikto web vulnerability scan — 8,102 checks, 17 vulnerabilities found

**Phase 3 — Exploitation**
- Hydra web brute force (14M+ attempts)
- Hydra SSH brute force (78 attempts)
- SQL injection testing against DVWA
- XSS payload testing

---

## Attack Statistics

| Metric | Result |
|--------|--------|
| Total Web Requests Logged | 21,568 |
| SSH Intrusion Attempts | 78 |
| Vulnerabilities Found | 17 |
| Brute Force Success | Yes (weak credentials detected) |
| Detection Rate | 100% |
| Attack Tools Detected | Nmap, Nikto, Hydra, curl |

---

## Defense Results

Every single attack was detected and logged in real time through the ELK Stack dashboards. ModSecurity WAF successfully identified and alerted on web attack patterns including SQL injection and XSS attempts. Cowrie honeypot captured attacker credentials and commands across all 78 SSH intrusion attempts.

---

## Files in This Repository

| File | Description |
|------|-------------|
| Network_diagram.png | Full network architecture diagram |
| Test-Incident_Report.docx | Complete incident report with findings |
| LOGS_SUMMARY.txt | Summary of all log files and statistics |
| dvwa_Cowrie_Nmap_scan.txt | Raw nmap scan output |
| cowrie_honeypot_logs.json | All 78 SSH honeypot capture events |

---

## Tools and Technologies

Kali Linux | Nmap | Nikto | Hydra | SQLMap | Apache | MySQL | DVWA | Cowrie | ModSecurity | Elasticsearch | Logstash | Kibana

---

## Connect

[LinkedIn](https://www.linkedin.com/in/paul-umeh) | [Main Portfolio](https://github.com/Paul-D3v/cybersecurity-portfolio)

---

*This project was conducted in a controlled, isolated lab environment for educational purposes only.*
