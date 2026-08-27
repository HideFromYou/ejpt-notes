# Web Brute Force

## Overview

Web brute-force attacks involve systematically attempting multiple credential combinations against web application authentication mechanisms.

During an authorized penetration test, brute-force testing can help identify weak passwords, weak authentication controls, and insufficient protections against repeated login attempts.

## Topics Covered

- Web Authentication
- Password Guessing
- Brute-Force Attacks
- Credential Testing
- Login Forms
- Wordlists
- Hydra
- Authentication Controls
- Rate Limiting
- Account Lockout

## Brute-Force Workflow

```text
Identify Login Page
        ↓
Identify Authentication Parameters
        ↓
Identify Valid Username
        ↓
Select Appropriate Wordlist
        ↓
Configure Brute-Force Tool
        ↓
Perform Controlled Credential Testing
        ↓
Identify Valid Credentials
        ↓
Validate Authentication
        ↓
Document Finding
```

## Commands

### Hydra

Hydra can perform automated password attacks against supported web authentication mechanisms.

For HTTP Basic Authentication:

```bash
hydra -l <username> -P <wordlist> http-get://<IP>/<path>
```

For HTTP POST forms, the request parameters and failure condition must be identified first.

```bash
hydra -l <username> -P <wordlist> <IP> http-post-form "<path>:<POST_PARAMETERS>:<FAILURE_STRING>"
```

Example structure:

```text
/path
username=^USER^&password=^PASS^
F=Invalid credentials
```

## Wordlists

Wordlists provide candidate usernames or passwords for credential testing.

```bash
# Count entries in a wordlist
wc -l <wordlist>

# View the contents of a wordlist
cat <wordlist>

# Search a wordlist for a specific value
grep "<value>" <wordlist>
```

## Authentication Testing

During web brute-force testing, examine:

```text
Login Parameters
Username Validation
Password Validation
Error Messages
Rate Limiting
Account Lockout
CAPTCHA
Session Handling
Authentication Responses
```

## Important Considerations

Brute-force attacks should be carefully controlled during an authorized assessment.

Consider:

- Scope and authorization
- Account lockout policies
- Rate limiting
- Request volume
- Service stability
- Appropriate wordlists
- Potential impact on user accounts

## Purpose

The purpose of this section is to understand how web authentication mechanisms can be tested for weak credentials and insufficient brute-force protections during an authorized penetration test.

Brute-force testing should be performed in a controlled manner and findings should be validated before being reported.