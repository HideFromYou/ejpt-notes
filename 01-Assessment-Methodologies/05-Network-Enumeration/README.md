# Network Enumeration

## Overview

Network enumeration is the process of actively interacting with discovered hosts and services to gather detailed information about the target environment.

This section focuses on identifying and enumerating network services, their versions, configurations, users, shares, and other information that can help determine potential attack paths.

## Topics Covered

- Network Enumeration Fundamentals
- Service Enumeration
- FTP Enumeration
- SSH Enumeration
- SMB Enumeration
- SMTP Enumeration
- DNS Enumeration
- SNMP Enumeration
- MySQL Enumeration
- HTTP and Web Server Enumeration
- Nmap Enumeration
- Metasploit-Based Enumeration

## Enumeration Workflow

```text
Discovered Host
      ↓
Open Ports
      ↓
Identify Services
      ↓
Service Version Detection
      ↓
Enumerate Service
      ↓
Identify Users, Shares, Configurations & Information
      ↓
Identify Potential Attack Paths
```

## Purpose

The purpose of this section is to understand how to move from basic port and service discovery to detailed enumeration of individual network services.

The information gathered during enumeration is used to identify misconfigurations, exposed resources, credentials, and potential vulnerabilities that can be investigated during vulnerability assessment and exploitation.