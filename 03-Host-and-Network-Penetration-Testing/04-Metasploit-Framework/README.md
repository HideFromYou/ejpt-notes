# Exploitation

## Overview

Exploitation is the process of using a discovered vulnerability or weakness to gain unauthorized functionality or access to a target system.

In a penetration test, exploitation follows reconnaissance, enumeration, and vulnerability assessment and is used to validate whether an identified vulnerability can actually be leveraged against the target.

## Topics Covered

- Exploitation Fundamentals
- Exploit Identification
- Exploit Selection
- Public Exploits
- Exploit Databases
- Manual Exploitation
- Remote Exploitation
- Local Exploitation
- Proof of Concept (PoC)
- Initial Access

## Commands

### Vulnerability and Exploit Research

```bash
# Search for known exploits
searchsploit <service>

# Search for a specific software version
searchsploit "<software> <version>"
```

### Nmap

```bash
# Identify services and versions
nmap -sC -sV <IP>

# Scan all TCP ports
nmap -p- <IP>
```

### Network Connections

```bash
# Connect to a remote TCP service
nc <IP> <PORT>
```

## Exploitation Workflow

```text
Identify Vulnerability
        ↓
Research Vulnerability
        ↓
Identify Available Exploit
        ↓
Analyze Exploit / PoC
        ↓
Configure Exploit
        ↓
Execute Exploit
        ↓
Validate Access
        ↓
Post-Exploitation
```

## Important Considerations

Before exploiting a vulnerability during an authorized assessment, consider:

- Target and service identification
- Vulnerability applicability
- Exploit requirements
- Potential impact
- Stability of the target
- Scope and authorization

## Purpose

The purpose of this section is to understand how vulnerabilities identified during an assessment can be validated and exploited in a controlled and authorized environment.

Successful exploitation can provide initial access and allow the assessment to continue into post-exploitation and privilege escalation.