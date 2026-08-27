# Pivoting and Port Forwarding

## Overview

Pivoting is a technique used during penetration testing to access systems or network segments that are not directly reachable from the attacker machine.

Port forwarding allows traffic destined for a specific port or service to be redirected through an accessible host, providing a way to reach otherwise inaccessible services.

## Topics Covered

- Pivoting
- Network Segmentation
- Internal Network Enumeration
- Port Forwarding
- SSH Port Forwarding
- Local Port Forwarding
- Remote Port Forwarding
- Proxychains
- Metasploit Pivoting
- Accessing Internal Services

## Commands

### SSH Local Port Forwarding

Forward a local port through an SSH connection to a service accessible from the remote host.

```bash
ssh -L <LOCAL_PORT>:<TARGET_IP>:<TARGET_PORT> <USER>@<SSH_SERVER>
```

Example:

```bash
ssh -L 8080:10.10.10.20:80 user@10.10.10.10
```

The service on the internal target can then be accessed through:

```text
127.0.0.1:8080
```

### SSH Remote Port Forwarding

Forward a port on the remote system back to a service accessible from the attacker machine.

```bash
ssh -R <REMOTE_PORT>:<TARGET_IP>:<TARGET_PORT> <USER>@<SSH_SERVER>
```

### Proxychains

Proxychains can route supported network connections through a configured proxy.

```bash
proxychains nmap -sT -Pn <IP>
```

The proxy configuration is typically located at:

```bash
/etc/proxychains.conf
```

### Metasploit Pivoting

Metasploit can be used to route traffic through an established session.

```text
# Display routing information
route

# Add a route through a session
route add <SUBNET> <NETMASK> <SESSION_ID>

# Display active sessions
sessions
```

## Pivoting Workflow

```text
Compromise Accessible Host
          ↓
Enumerate Internal Network
          ↓
Identify Internal Targets
          ↓
Identify Internal Services
          ↓
Establish Pivot
          ↓
Configure Port Forwarding / Routing
          ↓
Access Internal Services
          ↓
Continue Enumeration & Exploitation
```

## Purpose

The purpose of this section is to understand how compromised systems can be used as a bridge to access otherwise inaccessible network segments and services during an authorized penetration test.

Pivoting and port forwarding are particularly useful when network segmentation prevents direct communication between the attacker and internal targets.