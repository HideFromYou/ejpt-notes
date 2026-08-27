# File and System Information

## Overview

File and system information gathering involves collecting information about the target operating system, filesystem, running processes, installed software, and accessible files.

This information helps identify the target environment, understand system configuration, discover sensitive files, and identify potential attack paths.

## Topics Covered

- System Information
- Operating System Identification
- Hostname Information
- Kernel Information
- CPU and Memory Information
- Disk and Filesystem Information
- Running Processes
- Installed Software
- Environment Variables
- File and Directory Enumeration
- Sensitive Files
- File Permissions

## Commands

### System Information

```bash
# Display kernel and system information
uname -a

# Display the hostname
hostname

# Display operating system information
cat /etc/os-release
```

### CPU and Memory

```bash
# Display CPU information
lscpu

# Display memory usage
free -h
```

### Disk and Filesystem

```bash
# Display filesystem disk usage
df -h

# Display block devices
lsblk

# Display mounted filesystems
mount
```

### Running Processes

```bash
# Display running processes
ps aux

# Monitor running processes
top
```

### Files and Directories

```bash
# List files including hidden files
ls -la

# Search for files across the filesystem
find / -type f 2>/dev/null

# Search for SUID files
find / -type f -perm -4000 2>/dev/null
```

### Environment Variables

```bash
# Display environment variables
env

# Display the PATH environment variable
echo $PATH
```

### File Permissions

```bash
# Display detailed file permissions
ls -l

# Display permissions of a specific file
ls -l <file>
```

## Information Gathering Workflow

```text
Target Host
    ↓
Operating System Information
    ↓
Kernel & System Information
    ↓
CPU & Memory
    ↓
Users & Environment
    ↓
Processes & Services
    ↓
Files & Directories
    ↓
Permissions & Configuration
    ↓
Identify Potential Attack Paths
```

## Purpose

The purpose of this section is to understand how to gather detailed information about a target host and its filesystem.

The collected information can be used to identify system configurations, accessible resources, sensitive information, file permissions, and potential vulnerabilities for further enumeration and exploitation.