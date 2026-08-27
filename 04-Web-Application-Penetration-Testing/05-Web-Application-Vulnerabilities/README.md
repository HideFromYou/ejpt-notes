# Web Application Vulnerabilities

## Overview

Web application vulnerabilities are weaknesses in the design, implementation, configuration, or functionality of web applications that can be exploited to compromise confidentiality, integrity, or availability.

This section focuses on identifying and testing common web application vulnerabilities during an authorized penetration test.

## Topics Covered

- SQL Injection
- Cross-Site Scripting (XSS)
- Command Injection
- Authentication Vulnerabilities
- Authorization Vulnerabilities
- File Inclusion
- Security Misconfigurations
- Business Logic Vulnerabilities
- Input Validation
- Session Management

## Vulnerability Testing Workflow

```text
Map Application
      ↓
Identify Inputs & Parameters
      ↓
Understand Application Behavior
      ↓
Identify Potential Attack Surface
      ↓
Test Inputs
      ↓
Identify Vulnerability
      ↓
Validate Impact
      ↓
Document Evidence
      ↓
Recommend Remediation
```

## SQL Injection

SQL Injection occurs when untrusted user input is incorporated into SQL queries without adequate protection.

Potentially affected inputs include:

```text
Login Forms
Search Fields
URL Parameters
POST Parameters
Cookies
HTTP Headers
```

Basic testing examples:

```text
'
"
' OR '1'='1
```

Useful tool:

```bash
sqlmap -u "http://<IP>/<path>?id=<value>"
```

## Cross-Site Scripting (XSS)

Cross-Site Scripting occurs when attacker-controlled input is improperly included in web pages and interpreted as JavaScript by a victim's browser.

Common types include:

```text
Reflected XSS
Stored XSS
DOM-Based XSS
```

Basic testing payload:

```html
<script>alert(1)</script>
```

Common XSS testing locations include:

```text
Search Fields
Comments
User Profile Fields
URL Parameters
HTTP Headers
```

## Command Injection

Command injection occurs when an application passes user-controlled input to an operating-system command without adequate validation or sanitization.

Testing should focus on identifying parameters that may influence system commands.

Example characters commonly investigated during authorized testing include:

```text
;
&&
||
|
```

## Authentication Vulnerabilities

Authentication testing examines whether the application correctly verifies user identity.

Areas to test include:

```text
Weak Password Policies
Brute Force Protection
Default Credentials
Authentication Bypass
Password Reset Functionality
Session Handling
```

## Authorization Vulnerabilities

Authorization testing determines whether authenticated users can access resources or perform actions beyond their intended privileges.

Test for:

```text
Horizontal Privilege Escalation
Vertical Privilege Escalation
Insecure Direct Object References
Access Control Bypass
```

## File Inclusion

File inclusion vulnerabilities can occur when user-controlled input determines which files an application loads.

Common categories include:

```text
Local File Inclusion (LFI)
Remote File Inclusion (RFI)
```

Testing should identify parameters that control file paths and determine whether unauthorized files can be accessed.

## Security Misconfiguration

Common web application and server misconfigurations include:

```text
Default Credentials
Exposed Configuration Files
Directory Listing
Debug Information
Unnecessary Services
Missing Security Headers
Outdated Components
```

## Business Logic Vulnerabilities

Business logic vulnerabilities occur when an application implements a workflow or business rule incorrectly.

Testing should focus on understanding the intended application behavior and identifying ways to bypass restrictions or manipulate workflows.

Examples include:

```text
Price Manipulation
Workflow Bypass
Quantity Manipulation
Authorization Logic Flaws
Improper State Transitions
```

## Useful Tools

```text
Burp Suite
SQLmap
Nmap
Gobuster
Nikto
Browser Developer Tools
```

## Purpose

The purpose of this section is to understand how common web application vulnerabilities are identified, tested, validated, and documented during an authorized penetration test.

Manual testing and understanding of application behavior are essential for identifying vulnerabilities that automated scanners may miss.