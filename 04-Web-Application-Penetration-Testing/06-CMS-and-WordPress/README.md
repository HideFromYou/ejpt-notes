# CMS and WordPress

## Overview

Content Management Systems (CMS) are commonly used to build and manage websites. Their popularity makes them an important part of web application penetration testing.

WordPress is one of the most widely used CMS platforms and should be assessed for vulnerable components, exposed functionality, outdated versions, weak credentials, and configuration issues.

## Topics Covered

- Content Management Systems (CMS)
- WordPress
- CMS Identification
- WordPress Enumeration
- Plugins
- Themes
- Users
- Login Pages
- Version Identification
- Vulnerable Components
- CMS Misconfigurations

## CMS Testing Workflow

```text
Identify CMS
      ↓
Identify CMS Version
      ↓
Enumerate Users
      ↓
Enumerate Plugins & Themes
      ↓
Identify Versions
      ↓
Search for Known Vulnerabilities
      ↓
Test Configuration & Authentication
      ↓
Validate Findings
      ↓
Document Results
```

## Commands

### Identify the CMS

Use WhatWeb to identify technologies and possible CMS platforms.

```bash
whatweb http://<IP>/
```

### WordPress Enumeration

WPScan is commonly used to enumerate WordPress installations.

```bash
# Basic WordPress scan
wpscan --url http://<IP>/
```

Enumerate users:

```bash
wpscan --url http://<IP>/ --enumerate u
```

Enumerate plugins:

```bash
wpscan --url http://<IP>/ --enumerate p
```

Enumerate themes:

```bash
wpscan --url http://<IP>/ --enumerate t
```

### Directory Enumeration

```bash
gobuster dir -u http://<IP>/ -w <WORDLIST>
```

### HTTP Inspection

```bash
# Display HTTP headers
curl -I http://<IP>/

# Retrieve robots.txt
curl http://<IP>/robots.txt
```

## What to Look For

During CMS enumeration, investigate:

```text
CMS Type
CMS Version
Plugins
Plugin Versions
Themes
Theme Versions
Users
Login Pages
Administrative Panels
Exposed Files
Configuration Issues
Known Vulnerabilities
```

## WordPress Attack Surface

Important WordPress components include:

```text
WordPress Core
Plugins
Themes
Users
wp-admin
wp-login.php
wp-content
wp-includes
```

Outdated or vulnerable plugins and themes can introduce significant attack paths.

## Vulnerability Research

After identifying a component and version, search for known vulnerabilities.

```bash
searchsploit wordpress
searchsploit "<plugin> <version>"
```

## Purpose

The purpose of this section is to understand how CMS platforms, particularly WordPress, can be identified and enumerated during a web application penetration test.

Detailed enumeration of CMS components can reveal outdated software, vulnerable plugins or themes, exposed users, and other weaknesses that may provide opportunities for further testing.