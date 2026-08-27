# Privilege Escalation

## Overview

Privilege escalation is the process of obtaining higher privileges on a compromised system than those initially obtained.

This section covers techniques used to identify privilege escalation opportunities by analyzing system configurations, users, permissions, services, processes, and executable files.

## Topics Covered

- Privilege Escalation Fundamentals
- Local Privilege Escalation
- Linux Privilege Escalation
- Windows Privilege Escalation
- User and Group Privileges
- File Permissions
- SUID and SGID Binaries
- Scheduled Tasks
- Services
- Processes
- Misconfigurations
- Credential Discovery

## Commands

### Identify Current Privileges

```bash
# Identify the current user
whoami

# Display user and group information
id

# Display current groups
groups
```

### SUID Files

```bash
# Find SUID binaries
find / -perm -4000 -type f 2>/dev/null

# Find SGID binaries
find / -perm -2000 -type f 2>/dev/null
```

### File Permissions

```bash
# Display file permissions and ownership
ls -la

# Display permissions for a specific file
ls -l <file>
```

### Sudo Permissions

```bash
# Display commands the current user can execute with sudo
sudo -l
```

### Processes and Services

```bash
# Display running processes
ps aux

# Display listening services
ss -tulnp
```

### Scheduled Tasks

```bash
# Display current user's cron jobs
crontab -l

# Inspect system cron configuration
ls -la /etc/cron*
```

## Privilege Escalation Workflow

```text
Initial Access
      ↓
Identify Current User
      ↓
Enumerate Groups & Privileges
      ↓
Check Sudo Permissions
      ↓
Inspect Files & Permissions
      ↓
Search for SUID / SGID Binaries
      ↓
Enumerate Processes & Services
      ↓
Check Scheduled Tasks
      ↓
Identify Misconfigurations
      ↓
Exploit Privilege Escalation Path
      ↓
Obtain Higher Privileges
```

## Important Considerations

Privilege escalation techniques depend heavily on the target operating system, configuration, user privileges, and available services.

Enumeration should be performed before attempting exploitation so that the most appropriate and least disruptive escalation path can be identified.

## Purpose

The purpose of this section is to understand how to identify and exploit privilege escalation opportunities after obtaining initial access to a target system.

Successful privilege escalation can increase the level of access available to the penetration tester and provide access to additional system resources and sensitive information.