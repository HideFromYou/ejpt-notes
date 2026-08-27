# Web Application Penetration Testing

## Overview

Web application penetration testing focuses on identifying, validating, and exploiting security weaknesses in web applications and their supporting infrastructure.

This section covers the technologies used by web applications, reconnaissance, web server and directory enumeration, vulnerability scanning, common web application vulnerabilities, CMS and WordPress security, and web brute-force techniques.

## Topics Covered

- Web Application Technologies
- Web Reconnaissance
- Web Server and Directory Enumeration
- Web Vulnerability Scanning
- Web Application Vulnerabilities
- CMS and WordPress
- Web Brute Force

## Web Application Testing Workflow

```text
Target Web Application
        ↓
Identify Technologies
        ↓
Web Reconnaissance
        ↓
Web Server Enumeration
        ↓
Directory & File Enumeration
        ↓
Vulnerability Scanning
        ↓
Manual Vulnerability Testing
        ↓
Exploitation
        ↓
Validation & Evidence
        ↓
Reporting & Remediation
```

## Key Areas

### Web Application Technologies

Understand how web applications communicate and how their components interact.

```text
Client / Browser
       ↓
HTTP / HTTPS
       ↓
Web Server
       ↓
Web Application
       ↓
Database
```

Key concepts include:

```text
HTTP Methods
HTTP Headers
HTTP Status Codes
Cookies
Sessions
Web Servers
Front-End Technologies
Back-End Technologies
Databases
```

### Web Reconnaissance

Reconnaissance is used to identify the application's attack surface.

Information may include:

```text
Domains
Subdomains
IP Addresses
Technologies
Web Servers
HTTP Headers
Directories
Files
Endpoints
robots.txt
```

### Web Server and Directory Enumeration

Enumeration focuses on discovering resources that may not be directly linked from the main application.

```text
Directories
Files
Backup Files
Configuration Files
Login Pages
Administrative Panels
API Endpoints
Hidden Resources
```

### Web Vulnerability Scanning

Automated scanners can help identify potential weaknesses and misconfigurations.

Common tools include:

```text
Nmap
Nikto
Nessus
```

Scanner results should be manually validated before being treated as confirmed vulnerabilities.

### Web Application Vulnerabilities

Common vulnerabilities covered include:

```text
SQL Injection
Cross-Site Scripting (XSS)
Command Injection
Authentication Vulnerabilities
Authorization Vulnerabilities
File Inclusion
Security Misconfigurations
Business Logic Vulnerabilities
```

### CMS and WordPress

CMS assessments focus on identifying vulnerable components and configuration weaknesses.

Important WordPress components include:

```text
WordPress Core
Plugins
Themes
Users
wp-admin
wp-login.php
wp-content
wp-includes
```

### Web Brute Force

Authentication testing can include controlled credential testing against web login mechanisms.

Areas of interest include:

```text
Login Parameters
Username Validation
Password Validation
Rate Limiting
Account Lockout
CAPTCHA
Session Handling
Authentication Responses
```

## Tools

Common tools used during web application penetration testing include:

```text
Burp Suite
Nmap
Gobuster
Nikto
WhatWeb
WPScan
SQLmap
Hydra
Nessus
```

## Common Commands

### HTTP Requests

```bash
curl -I http://<IP>/
curl -v http://<IP>/
```

### Technology Identification

```bash
whatweb http://<IP>/
```

### Directory Enumeration

```bash
gobuster dir -u http://<IP>/ -w <WORDLIST>
```

### Service Enumeration

```bash
nmap -sC -sV -p 80,443 <IP>
```

### Web Server Scanning

```bash
nikto -h http://<IP>
```

### WordPress Enumeration

```bash
wpscan --url http://<IP>/
```

### SQL Injection Testing

```bash
sqlmap -u "http://<IP>/<path>?id=<value>"
```

## Chapters

- [Web Application Technologies](./01-Web-Application-Technologies/)
- [Web Reconnaissance](./02-Web-Reconnaissance/)
- [Web Server and Directory Enumeration](./03-Web-Server-and-Directory-Enumeration/)
- [Web Vulnerability Scanning](./04-Web-Vulnerability-Scanning/)
- [Web Application Vulnerabilities](./05-Web-Application-Vulnerabilities/)
- [CMS and WordPress](./06-CMS-and-WordPress/)
- [Web Brute Force](./07-Web-Brute-Force/)

## Purpose

The purpose of this section is to develop practical skills for assessing web applications, identifying vulnerabilities, validating their impact, and documenting findings during an authorized penetration test.

The techniques covered in this section build upon reconnaissance and enumeration to identify potential vulnerabilities and attack paths within web applications.