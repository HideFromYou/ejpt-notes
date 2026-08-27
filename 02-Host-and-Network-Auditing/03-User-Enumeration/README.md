# User Enumeration

## Overview

User enumeration is the process of identifying users and accounts that exist on a target system.

Enumerating users can provide valuable information about the target environment and may help identify valid accounts for authentication testing, privilege analysis, and further penetration testing activities.

## Topics Covered

- Local User Enumeration
- Current User Identification
- User IDs and Groups
- Logged-In Users
- Local User Accounts
- Local Groups
- Account Information

## Commands

### Current User

```bash
# Display the current username
whoami

# Display user ID and group information
id

# Display groups associated with the current user
groups
```

### Logged-In Users

```bash
# Display currently logged-in users
who

# Display logged-in users and their activity
w
```

### Local Users

```bash
# Display local user accounts
cat /etc/passwd

# Search for a specific user
grep "<username>" /etc/passwd
```

### Local Groups

```bash
# Display local groups
cat /etc/group

# Display groups for the current user
groups
```

### User and Account Information

```bash
# Display information about a user
id <username>

# Check the user's home directory
ls -la /home/<username>
```

## Enumeration Workflow

```text
Target Host
    ↓
Identify Current User
    ↓
Enumerate User Accounts
    ↓
Enumerate Groups
    ↓
Identify Logged-In Users
    ↓
Analyze User Privileges
    ↓
Identify Potential Attack Paths
```

## Purpose

The purpose of this section is to understand how to enumerate users and groups on a target system.

User information can help identify valid accounts, determine group memberships and privileges, and provide useful information for subsequent credential attacks and privilege escalation.