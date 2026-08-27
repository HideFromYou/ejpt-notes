# System and Host-Based Attacks

## Overview

System and host-based attacks focus on identifying and exploiting weaknesses in individual target systems.

This section covers common attack techniques against host operating systems, applications, services, and configurations after the target has been enumerated.

## Topics Covered

- System-Based Attacks
- Host-Based Attacks
- Exploiting Vulnerable Services
- Exploiting Misconfigurations
- Local System Enumeration
- Vulnerable Applications
- Service Exploitation
- Initial Access

## Commands

### System Enumeration

```bash
# Identify the current user
whoami

# Display user and group information
id

# Display operating system and kernel information
uname -a

# Display running processes
ps aux

# Display system information
hostname
cat /etc/os-release
```

### Network and Service Enumeration

```bash
# Display listening services
ss -tulnp

# Enumerate services and versions
nmap -sC -sV <IP>
```

### Vulnerability Identification

```bash
# Search for known exploits
searchsploit <service>

# Search for a specific software version
searchsploit "<software> <version>"
```

## Attack Workflow

```text
Target Host
    ↓
System Enumeration
    ↓
Service Enumeration
    ↓
Identify Vulnerabilities
    ↓
Research Potential Exploits
    ↓
Exploit Vulnerable Service
    ↓
Obtain Initial Access
    ↓
Post-Exploitation
```

## Purpose

The purpose of this section is to understand how weaknesses in host systems, applications, services, and configurations can be identified and exploited during an authorized penetration test.

The techniques covered here build upon the enumeration and vulnerability assessment stages and lead toward gaining initial access to a target system.