# Web Reconnaissance

## Overview

Web reconnaissance is the process of gathering information about a web application and its underlying infrastructure before performing vulnerability testing.

The objective is to identify the application's attack surface, technologies, domains, subdomains, endpoints, directories, files, and exposed services.

## Topics Covered

- Web Reconnaissance
- Information Gathering
- Domain Enumeration
- Subdomain Enumeration
- Technology Identification
- Web Server Identification
- HTTP Headers
- Robots.txt
- Application Endpoints
- Publicly Exposed Information

## Reconnaissance Workflow

```text
Target Domain
      ↓
Domain Information
      ↓
Subdomain Enumeration
      ↓
Technology Identification
      ↓
Web Server Identification
      ↓
HTTP Header Analysis
      ↓
Endpoint & Directory Discovery
      ↓
Map Web Attack Surface
```

## Commands

### HTTP Headers

Use `curl` to inspect HTTP response headers.

```bash
# Display HTTP response headers
curl -I http://<DOMAIN>

# Display detailed HTTP request and response information
curl -v http://<DOMAIN>
```

### Technology Identification

Use WhatWeb to identify technologies used by a web application.

```bash
whatweb http://<DOMAIN>
```

### Web Server and Service Enumeration

Use Nmap to identify exposed web services.

```bash
# Identify services and versions
nmap -sC -sV -p 80,443 <IP>

# Run HTTP enumeration scripts
nmap --script http-enum <IP>
```

### Directory Enumeration

Gobuster can be used to discover directories and files.

```bash
gobuster dir -u http://<DOMAIN>/ -w <WORDLIST>
```

For common file extensions:

```bash
gobuster dir -u http://<DOMAIN>/ -w <WORDLIST> -x php,txt,html
```

### robots.txt

The `robots.txt` file can contain paths that search engine crawlers should avoid indexing.

```bash
curl http://<DOMAIN>/robots.txt
```

## Information to Collect

During web reconnaissance, record useful information such as:

```text
Domain
Subdomains
IP Addresses
Web Server
Technologies
HTTP/HTTPS
Open Ports
Directories
Files
Endpoints
HTTP Headers
robots.txt
```

## Purpose

The purpose of this section is to understand how to systematically gather information about a web application before vulnerability testing.

Effective reconnaissance helps build an accurate attack-surface map and provides information that can guide subsequent enumeration, vulnerability discovery, and exploitation.