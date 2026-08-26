# Footprinting and Scanning

## Overview

Footprinting and scanning are used to identify and characterize the target's network infrastructure, hosts, ports, operating systems, and running services.

This section covers network discovery and scanning techniques used to determine which systems are reachable, which ports are open, and which services and operating systems may be present on a target.

## Topics Covered

- Footprinting Fundamentals
- Host Discovery
- Network Discovery
- Port Scanning
- TCP Scanning
- UDP Scanning
- Service Detection
- Service Version Detection
- Operating System Detection
- Nmap
- Nmap Scan Types
- Nmap Timing and Scan Optimization
- Firewall Detection and IDS Evasion

## Scanning Workflow

```text
Target
  ↓
Host Discovery
  ↓
Port Scanning
  ↓
Service Detection
  ↓
Version Detection
  ↓
Operating System Detection
  ↓
Further Enumeration
```

## Purpose

The purpose of this section is to understand how to systematically discover hosts, ports, services, and operating systems during a penetration test.

The information gathered during scanning provides the foundation for detailed service enumeration and subsequent vulnerability assessment.