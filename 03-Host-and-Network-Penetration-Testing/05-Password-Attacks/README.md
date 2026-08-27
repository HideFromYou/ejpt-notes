# Password Attacks

## Overview

Password attacks involve attempting to discover, validate, or recover credentials that can be used to authenticate to target systems and services.

This section covers common password attack techniques used during authorized penetration testing, including password guessing, brute-force attacks, password spraying, and password cracking.

## Topics Covered

- Password Attacks
- Brute-Force Attacks
- Password Guessing
- Password Spraying
- Credential Attacks
- Password Cracking
- Wordlists
- Hash Cracking
- Hydra
- Hashcat

## Commands

### Hydra

Hydra can be used to perform online password attacks against supported network services.

```bash
# Brute-force SSH credentials
hydra -l <username> -P <wordlist> ssh://<IP>

# Brute-force a service using a username and password list
hydra -L <userlist> -P <wordlist> <IP> <service>
```

### Hashcat

Hashcat can be used to perform offline password cracking against password hashes.

```bash
# Crack a hash using a wordlist
hashcat <hash_file> <wordlist>

# Display supported hash modes
hashcat --help
```

### Wordlists

Common wordlists can be used to test passwords during authorized assessments.

```bash
# View a wordlist
cat <wordlist>

# Count lines in a wordlist
wc -l <wordlist>
```

## Password Attack Workflow

```text
Identify Authentication Service
          ↓
Identify Valid Username
          ↓
Obtain or Select Wordlist
          ↓
Choose Attack Technique
          ↓
Password Guessing / Brute Force
          ↓
Validate Credentials
          ↓
Authenticate to Target
          ↓
Continue Assessment
```

## Important Considerations

Password attacks should be carefully controlled during an authorized assessment.

Consider:

- Scope and authorization
- Account lockout policies
- Rate limiting
- Service availability
- Appropriate wordlists
- Potential impact on the target

## Purpose

The purpose of this section is to understand how password-based authentication can be tested during an authorized penetration test.

Password attacks can provide valid credentials that may enable access to network services or support further exploitation and privilege escalation.