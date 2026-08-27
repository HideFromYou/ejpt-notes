# Web Application Technologies

## Overview

Understanding web application technologies is an essential part of web application penetration testing.

Before testing for vulnerabilities, it is important to understand how clients, web servers, applications, databases, and HTTP communication work together.

## Topics Covered

- Client-Server Architecture
- HTTP
- HTTPS
- HTTP Requests
- HTTP Responses
- HTTP Methods
- HTTP Headers
- Status Codes
- Cookies
- Sessions
- Web Servers
- Web Applications
- Databases
- Front-End Technologies
- Back-End Technologies

## Web Application Architecture

```text
Client / Browser
       ↓
HTTP / HTTPS
       ↓
Web Server
       ↓
Web Application
       ↓
Database
```

## HTTP Methods

Common HTTP methods encountered during web application testing include:

```text
GET
POST
PUT
PATCH
DELETE
HEAD
OPTIONS
```

### GET

Used to request a resource from a server.

```http
GET /index.php HTTP/1.1
Host: example.com
```

### POST

Used to submit data to a server.

```http
POST /login.php HTTP/1.1
Host: example.com
Content-Type: application/x-www-form-urlencoded

username=user&password=password
```

## HTTP Response Codes

Common status codes:

```text
200 OK
201 Created
301 Moved Permanently
302 Found
400 Bad Request
401 Unauthorized
403 Forbidden
404 Not Found
500 Internal Server Error
```

## Useful Commands

### curl

`curl` can be used to interact with web servers directly from the command line.

```bash
# Make a basic HTTP request
curl http://<IP>/

# Display HTTP response headers
curl -I http://<IP>/

# Display the full HTTP request and response
curl -v http://<IP>/

# Send a GET request
curl -X GET http://<IP>/

# Send a POST request
curl -X POST -d "username=user&password=password" http://<IP>/login
```

### Nmap

```bash
# Identify web services and versions
nmap -p 80,443 -sC -sV <IP>

# Run HTTP enumeration scripts
nmap --script http-enum <IP>
```

### WhatWeb

```bash
# Identify technologies used by a web application
whatweb http://<IP>/
```

## Cookies and Sessions

Cookies are commonly used by web applications to maintain state between HTTP requests.

During a penetration test, cookies and session mechanisms should be examined for weaknesses such as:

- Missing security attributes
- Session management weaknesses
- Predictable session identifiers
- Improper session invalidation
- Authentication-related weaknesses

Useful cookie attributes include:

```text
Secure
HttpOnly
SameSite
```

## Web Application Testing Workflow

```text
Identify Application
        ↓
Identify Technologies
        ↓
Analyze HTTP Requests
        ↓
Analyze HTTP Responses
        ↓
Identify Authentication & Sessions
        ↓
Map Application Functionality
        ↓
Enumerate Attack Surface
        ↓
Test for Vulnerabilities
```

## Purpose

The purpose of this section is to build a foundation for understanding how modern web applications communicate and operate.

Understanding HTTP, web technologies, sessions, and application architecture helps identify potential attack surfaces and provides the foundation for subsequent web application enumeration and vulnerability testing.