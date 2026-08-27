# Host and Network Penetration Testing

## Overview

Host and network penetration testing focuses on identifying and exploiting vulnerabilities in systems, network services, and infrastructure.

This section covers practical penetration testing techniques including system and host-based attacks, network-based attacks, exploitation, Metasploit Framework, password attacks, post-exploitation, privilege escalation, and pivoting.

## Topics Covered

- System and Host-Based Attacks
- Network-Based Attacks
- Exploitation
- Metasploit Framework
- Password Attacks
- Post-Exploitation
- Privilege Escalation
- Pivoting and Port Forwarding

## Penetration Testing Workflow

```text
Target
  ↓
Host & Network Enumeration
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
Credential & System Enumeration
  ↓
Pivoting & Port Forwarding
  ↓
Further Attack Paths
```

## Commands

### Exploitation and Enumeration

Common commands and utilities used during authorized penetration testing and lab environments.

```bash
# Connect to a remote service
nc <IP> <PORT>

# Enumerate services with Nmap
nmap -sC -sV <IP>

# Search for known vulnerabilities
searchsploit <service>
```

### Metasploit Framework

```bash
# Start Metasploit Framework
msfconsole

# Search for modules
search <term>

# Select a module
use <module>

# Display module information
info

# Display module options
show options

# Set a module option
set <OPTION> <VALUE>

# Execute the module
run
```

### Password Attacks

Common tools used for authorized password auditing and credential testing.

```bash
# Hydra
hydra -l <username> -P <wordlist> <IP> <service>

# Hashcat
hashcat <hash_file> <wordlist>
```

### Post-Exploitation and Privilege Escalation

After obtaining access to a target, system information and privileges can be enumerated to identify further attack paths.

```bash
# Identify current user
whoami

# Display user and group information
id

# Display system information
uname -a

# Display running processes
ps aux

# Search for SUID binaries
find / -perm -4000 -type f 2>/dev/null
```

### Pivoting and Port Forwarding

Pivoting can be used during authorized assessments to access network segments that are not directly reachable from the attacker machine.

Common tools and techniques include:

```text
SSH Port Forwarding
Proxychains
Metasploit Pivoting
Port Forwarding
```

## Chapters

- [System and Host-Based Attacks](./01-System-and-Host-Based-Attacks/)
- [Network-Based Attacks](./02-Network-Based-Attacks/)
- [Exploitation](./03-Exploitation/)
- [Metasploit Framework](./04-Metasploit-Framework/)
- [Password Attacks](./05-Password-Attacks/)
- [Post-Exploitation](./06-Post-Exploitation/)
- [Privilege Escalation](./07-Privilege-Escalation/)
- [Pivoting and Port Forwarding](./08-Pivoting-and-Port-Forwarding/)

## Purpose

The purpose of this section is to develop practical skills for identifying, exploiting, and extending access to vulnerable hosts and network services during an authorized penetration test.

The techniques covered here build upon reconnaissance, scanning, enumeration, and vulnerability assessment to progress toward exploitation and post-exploitation activities.