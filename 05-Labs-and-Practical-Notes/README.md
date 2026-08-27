# Labs and Practical Notes

## Overview

This section contains practical penetration testing exercises, lab notes, commands, workflows, and lessons learned.

The purpose of this section is to connect the theoretical material covered in the main eJPT sections with hands-on practice.

## Categories

- [Methodology](./Methodology/)
- [Network Pentesting](./Network-Pentesting/)
- [Host Pentesting](./Host-Pentesting/)
- [Web Pentesting](./Web-Pentesting/)

## Practical Workflow

```text
Reconnaissance
      ↓
Scanning
      ↓
Enumeration
      ↓
Vulnerability Identification
      ↓
Exploitation
      ↓
Initial Access
      ↓
Post-Exploitation
      ↓
Privilege Escalation
      ↓
Further Access
      ↓
Documentation
```

## Methodology

The methodology section contains practical notes related to the overall penetration testing process.

Topics include:

```text
Information Gathering
Reconnaissance
Scanning
Enumeration
Vulnerability Assessment
Attack Surface Mapping
```

## Network Pentesting

The network penetration testing section contains practical exercises involving:

```text
Host Discovery
Port Scanning
Service Enumeration
Network Service Exploitation
Password Attacks
Metasploit
Pivoting
Port Forwarding
```

## Host Pentesting

The host penetration testing section contains practical exercises involving:

```text
System Enumeration
User Enumeration
Credential Discovery
File Enumeration
Exploitation
Post-Exploitation
Privilege Escalation
```

## Web Pentesting

The web penetration testing section contains practical exercises involving:

```text
Web Reconnaissance
Technology Identification
Directory Enumeration
Web Vulnerability Scanning
SQL Injection
XSS
Authentication Testing
CMS Enumeration
WordPress
Web Brute Force
```

## Lab Notes

When documenting a completed lab, use the following structure:

```text
Lab Name
Platform
Objective
Target
Tools Used
Commands
Methodology
Enumeration
Findings
Exploitation
Post-Exploitation
Privilege Escalation
Lessons Learned
```

## Commands

Commands used during practical exercises should be documented together with their purpose.

Example:

```bash
# Identify services running on the target
nmap -sC -sV <IP>

# Enumerate web directories
gobuster dir -u http://<IP>/ -w <WORDLIST>

# Identify web technologies
whatweb http://<IP>/
```

## Lab Status

```text
⬜ Not Started
🟨 In Progress
🟩 Completed
```

## Purpose

The purpose of this section is to document hands-on penetration testing experience and reinforce the concepts covered throughout the eJPT knowledge base.

The practical notes should focus on methodology, reasoning, commands, findings, and lessons learned rather than reproducing third-party walkthroughs.

All labs and techniques must be performed only in authorized training or testing environments.