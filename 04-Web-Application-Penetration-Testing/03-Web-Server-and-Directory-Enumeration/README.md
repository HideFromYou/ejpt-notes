# Web Server and Directory Enumeration

## Overview

Web server and directory enumeration focuses on discovering directories, files, endpoints, and information exposed by a web server.

The goal is to expand the application's attack surface and identify resources that may not be directly linked from the main application.

## Topics Covered

- Web Server Enumeration
- Directory Enumeration
- File Enumeration
- Hidden Resources
- HTTP Status Codes
- Directory Discovery
- File Extensions
- Web Server Information

## Enumeration Workflow

```text
Web Server
    ↓
Identify Web Service
    ↓
Identify Server Information
    ↓
Enumerate Directories
    ↓
Enumerate Files
    ↓
Test File Extensions
    ↓
Analyze Responses
    ↓
Identify Interesting Resources
```

## Commands

### Nmap

Identify web services and perform basic HTTP enumeration.

```bash
# Identify services and versions
nmap -sC -sV -p 80,443 <IP>

# Enumerate common HTTP resources
nmap --script http-enum <IP>
```

### Gobuster

Gobuster can be used to discover directories and files.

```bash
# Directory enumeration
gobuster dir -u http://<IP>/ -w <WORDLIST>
```

Enumerate common file extensions:

```bash
gobuster dir -u http://<IP>/ -w <WORDLIST> -x php,txt,html
```

Specify additional options when required:

```bash
gobuster dir -u http://<IP>/ -w <WORDLIST> -t 50
```

### Curl

Use `curl` to manually inspect discovered resources.

```bash
# Request a resource
curl http://<IP>/<PATH>

# Display response headers
curl -I http://<IP>/<PATH>

# Display detailed request and response information
curl -v http://<IP>/<PATH>
```

### robots.txt

Check whether the web server exposes a `robots.txt` file.

```bash
curl http://<IP>/robots.txt
```

## What to Look For

During enumeration, pay attention to:

```text
Directories
Files
Backup Files
Configuration Files
Login Pages
Administrative Panels
robots.txt
Source Code
API Endpoints
Different File Extensions
Interesting HTTP Status Codes
```

## HTTP Status Codes

Status codes can help interpret enumeration results.

```text
200 OK
301 Moved Permanently
302 Found
403 Forbidden
404 Not Found
500 Internal Server Error
```

A `403 Forbidden` response can still indicate that a resource exists even though access is denied.

## Purpose

The purpose of this section is to understand how to systematically enumerate web servers and discover resources that may expand the application's attack surface.

Directory and file enumeration can reveal hidden functionality, administrative interfaces, configuration files, and other resources that may be relevant during subsequent vulnerability testing.