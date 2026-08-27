# Host and Network Auditing

## Overview

Host and network auditing focuses on gathering detailed information from target systems and networks during a penetration test.

This section covers techniques used to identify system and network information, enumerate users, identify credentials and hashes, and transfer files between systems.

## Topics Covered

- File and System Information
- Network Information
- User Enumeration
- Credentials and Hashes
- File Transfer

## Auditing Workflow

```text
Target System
      ↓
File & System Information
      ↓
Network Information
      ↓
User Enumeration
      ↓
Credentials & Hashes
      ↓
File Transfer
      ↓
Further Enumeration & Exploitation
```

## Commands

### File and System Information

Common commands used to gather information about the target system, operating system, filesystem, processes, and accessible files.

```bash
# System information
uname -a
hostname
cat /etc/os-release

# CPU and memory information
lscpu
free -h

# Disk and filesystem information
df -h
lsblk
mount

# Running processes
ps aux
top

# Files and directories
ls -la
find / -type f 2>/dev/null

# SUID files
find / -type f -perm -4000 2>/dev/null

# Environment variables
env
echo $PATH
```

### Network Information

Commands used to identify network interfaces, IP addresses, routing information, and network connections.

```bash
# Network interfaces and IP addresses
ip addr
ip a

# Routing information
ip route
route -n

# Network connections
ss -tulnp
netstat -tulnp

# DNS configuration
cat /etc/resolv.conf
```

### User Enumeration

Commands used to identify local users, groups, and currently logged-in users.

```bash
# Current user
whoami

# Current user ID and groups
id

# Logged-in users
who
w

# Local users
cat /etc/passwd

# Local groups
cat /etc/group

# Current user's groups
groups
```

### Credentials and Hashes

Commands and locations commonly used during authorized security assessments to identify credential-related information.

```bash
# Password hash database
cat /etc/shadow

# Search for potentially sensitive files
find / -type f \( -name "*.conf" -o -name "*.config" -o -name "*.ini" \) 2>/dev/null

# Search for common credential-related keywords
grep -RniE "password|passwd|username|credential" /etc 2>/dev/null
```

Access to credential stores should only be performed against systems where explicit authorization has been provided.

### File Transfer

Common utilities used to transfer files between systems during authorized penetration testing and lab environments.

```bash
# Download a file with wget
wget http://<IP>/<file>

# Download a file with curl
curl http://<IP>/<file> -o <file>

# Transfer files with SCP
scp <file> <user>@<IP>:/tmp/

# Transfer files from a remote host
scp <user>@<IP>:/path/to/file .
```

## Purpose

The purpose of this section is to develop the ability to gather useful information from hosts and networks after initial discovery.

The information collected during auditing can help identify users, services, credentials, system configurations, accessible resources, and potential attack paths for subsequent penetration testing activities.