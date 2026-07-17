# Task 6 - Probing Metasploitable VM

## Objective
Perform vulnerability assessment and service enumeration on a *Metasploitable 2* virtual machine using industry-standard scanning and enumeration tools.

## Tools Used
- *OpenVAS (Greenbone)* – Automated vulnerability scanning
- *Nikto* – Web server vulnerability scanning
- *Netcat (nc)* – Manual banner grabbing / service enumeration

## Target
| Detail | Value |
|---|---|
| Operating System | Metasploitable 2 |
| Target Service | Apache Web Server (Port 80) |

## Files Included
| File | Description |
|---|---|
| openvas-report.pdf | OpenVAS vulnerability assessment report |
| nikto-report.html | Nikto web server scan report |
| banner-grab.png | Banner grabbing screenshot using Netcat |

## Tasks Completed
- [x] Performed a vulnerability scan using OpenVAS
- [x] Generated an HTML web server scan report using Nikto
- [x] Grabbed a service banner using Netcat
- [x] Uploaded all required deliverables to this repository

## Methodology

### 1. OpenVAS Vulnerability Scan
A full vulnerability assessment was run against the Metasploitable 2 target IP using OpenVAS (Greenbone Vulnerability Manager). The scan enumerated open ports, running services, and known CVEs, with results exported as openvas-report.pdf.

### 2. Nikto Web Server Scan
Nikto was used to specifically probe the Apache web server running on port 80, checking for outdated software versions, dangerous files, misconfigurations, and known vulnerabilities. Results were exported in HTML format as nikto-report.html.

bash
nikto -h <target-ip> -o nikto-report.html -Format htm


### 3. Banner Grabbing with Netcat
Netcat was used to manually connect to the Apache service on port 80 and capture the service banner to confirm the server version and validate findings from the automated scans.

bash
nc -v <target-ip> 80
HEAD / HTTP/1.0


A screenshot of this process is included as banner-grab.png.

## Key Findings (Summary)
Metasploitable 2 is an intentionally vulnerable Linux VM used for security training. Scans against its Apache service typically reveal:
- Outdated Apache and PHP versions with known CVEs
- Directory listing enabled
- Presence of default/test files
- Missing security headers

(Refer to the attached reports for full, detailed findings.)

## Disclaimer
This assessment was performed in an isolated lab environment against *Metasploitable 2*, a deliberately vulnerable virtual machine designed for security training purposes. No real-world or production systems were targeted.

## Course Context
This repository was created as part of the *Cyber Security Analyst* course practical assignment — *Task 6: Probing Metasploitable VM*.
