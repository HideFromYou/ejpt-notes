# Network Information

## Overview

Network information gathering involves identifying the network configuration of a target host and understanding how the system communicates with other hosts and networks.

This information can reveal IP addresses, network interfaces, routing information, DNS configuration, active connections, and listening services.

## Topics Covered

- Network Interfaces
- IP Address Information
- Network Configuration
- Routing Information
- DNS Configuration
- Network Connections
- Listening Services
- Network Enumeration

## Commands

### Network Interfaces and IP Addresses

```bash
# Display network interfaces and IP addresses
ip addr

# Short form
ip a
```

### Routing Information

```bash
# Display the routing table
ip route

# Display routing information
route -n
```

### Network Connections and Listening Services

```bash
# Display listening TCP and UDP sockets
ss -tulnp

# Display network connections and listening ports
netstat -tulnp
```

### DNS Configuration

```bash
# Display configured DNS servers
cat /etc/resolv.conf
```

## Network Information Workflow

```text
Target Host
    ↓
Identify Network Interfaces
    ↓
Identify IP Addresses
    ↓
Inspect Routing Table
    ↓
Identify DNS Configuration
    ↓
Inspect Network Connections
    ↓
Identify Listening Services
    ↓
Map Potential Attack Paths
```

## Purpose

The purpose of this section is to understand how to identify and analyze the network configuration of a target host.

The collected information can help determine how the host communicates with other systems, identify accessible networks and services, and support further enumeration and exploitation.