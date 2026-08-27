# Credentials and Hashes

## Overview

Credentials and hashes are valuable pieces of information that may be discovered during host auditing and enumeration.

This section covers the identification of credential-related information, password hashes, and files or configurations that may contain sensitive authentication data.

## Topics Covered

- Credentials
- Passwords
- Password Hashes
- `/etc/passwd`
- `/etc/shadow`
- Credential Discovery
- Sensitive Configuration Files
- Password Hash Identification
- Credential-Based Attack Paths

## Commands

### Password and User Databases

```bash
# Display local user accounts
cat /etc/passwd

# Display password hashes
cat /etc/shadow
```

Access to `/etc/shadow` normally requires elevated privileges.

### Searching for Credentials

```bash
# Search configuration files for common credential keywords
grep -RniE "password|passwd|username|credential" /etc 2>/dev/null

# Search for configuration files
find / -type f \( -name "*.conf" -o -name "*.config" -o -name "*.ini" \) 2>/dev/null
```

### File Permissions

```bash
# Check permissions and ownership
ls -l <file>

# Check permissions of sensitive files
ls -l /etc/passwd /etc/shadow
```

## Credential Enumeration Workflow

```text
Target Host
    ↓
Identify Users
    ↓
Identify Credential Stores
    ↓
Search Configuration Files
    ↓
Identify Passwords / Hashes
    ↓
Analyze Hashes
    ↓
Identify Potential Credential Attack Paths
```

## Security Considerations

Credentials and password hashes are sensitive information.

Credential discovery and hash collection should only be performed against systems where explicit authorization has been provided.

## Purpose

The purpose of this section is to understand where credential-related information may be stored on a Linux system and how to identify it during an authorized penetration test.

Discovered credentials or hashes may provide authentication opportunities or help identify further attack paths during the assessment.