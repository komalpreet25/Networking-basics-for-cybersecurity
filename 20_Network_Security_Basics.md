# Network Security Basics

## Description

Network Security Basics covers the fundamental principles and practices used to protect computer networks from unauthorized access, attacks, data breaches, and misuse.

It includes concepts like CIA Triad, authentication, encryption, firewalls, and common cyber attacks.

---

# Why Network Security is Important

Networks carry sensitive data such as:

* Personal information
* Financial data
* Login credentials
* Business data
* Government records

Without security, this data can be stolen or misused.

---

# CIA Triad

The CIA Triad is the foundation of cybersecurity.

---

## 1. Confidentiality

Ensures that data is only accessible to authorized users.

### Example:

```text id="c1a1"
Only you can access your account data
```

### Techniques:

* Encryption
* Access control
* Password protection

---

## 2. Integrity

Ensures data is not modified or tampered with.

### Example:

```text id="c1a2"
Bank balance should not be changed without permission
```

### Techniques:

* Hashing
* Checksums
* Digital signatures

---

## 3. Availability

Ensures systems and data are available when needed.

### Example:

```text id="c1a3"
Website should not go offline during usage
```

### Techniques:

* Load balancing
* Redundancy
* DDoS protection

---

# AAA Security Model

AAA stands for:

---

## 1. Authentication

Verifying identity.

### Example:

```text id="a1"
Username + Password login
```

---

## 2. Authorization

Determining access rights.

### Example:

```text id="a2"
Admin can delete data, user cannot
```

---

## 3. Accounting

Tracking user activity.

### Example:

```text id="a3"
Login logs and activity logs
```

---

# Encryption

Encryption converts readable data into unreadable format.

---

## Example:

```text id="e1"
Hello → X9@k#2
```

---

## Types of Encryption

### Symmetric Encryption

Same key used for encryption and decryption.

---

### Asymmetric Encryption

Uses two keys:

* Public Key
* Private Key

---

# Hashing

Hashing converts data into fixed-length output.

---

## Example:

```text id="h1"
password123 → 482c811da5d5b4bc6d497ffa98491e38
```

---

## Features:

* One-way function
* Cannot be reversed
* Same input gives same output

---

## Common Hashing Algorithms:

* MD5 (weak)
* SHA-256 (strong)
* SHA-3 (modern)

---

# Authentication Methods

---

## 1. Password-Based Authentication

Most common method.

---

## 2. Multi-Factor Authentication (MFA)

Uses multiple verification steps.

### Example:

```text id="m1"
Password + OTP + Fingerprint
```

---

## 3. Biometric Authentication

Uses physical traits:

* Fingerprint
* Face recognition
* Iris scan

---

# Common Network Attacks

---

## 1. Phishing

Fake websites or emails to steal credentials.

---

## 2. DDoS Attack

Overloading a system with traffic.

```text id="d1"
Millions of requests → Server crash
```

---

## 3. Man-in-the-Middle (MITM)

Attacker intercepts communication.

---

## 4. Malware

Malicious software such as:

* Virus
* Worm
* Trojan

---

## 5. Brute Force Attack

Trying many passwords until correct one is found.

---

## 6. DNS Spoofing

Redirecting users to fake websites.

---

## 7. ARP Spoofing

Fake ARP responses to intercept traffic.

---

# Firewalls

A firewall filters network traffic based on rules.

---

## Example:

```text id="f1"
Allow HTTPS (443)
Block Telnet (23)
```

---

## Types:

* Packet Filtering Firewall
* Stateful Firewall
* Next-Generation Firewall (NGFW)

---

# IDS and IPS

---

## IDS (Intrusion Detection System)

Detects and alerts attacks.

---

## IPS (Intrusion Prevention System)

Detects and blocks attacks.

---

# VPN (Virtual Private Network)

Creates a secure encrypted tunnel over the internet.

---

## Benefits:

* Privacy
* Security
* Remote access

---

# Secure Network Practices

---

## 1. Strong Passwords

Use complex passwords:

```text id="s1"
A@12xY#9Z
```

---

## 2. Regular Updates

Keep systems updated to fix vulnerabilities.

---

## 3. Network Segmentation

Divide networks into smaller parts.

---

## 4. Least Privilege Principle

Give minimum required access.

---

## 5. Monitoring and Logging

Track network activity for suspicious behavior.

---

# Port Security Basics

Common insecure ports:

| Port | Service |
| ---- | ------- |
| 21   | FTP     |
| 23   | Telnet  |
| 80   | HTTP    |
| 3389 | RDP     |

Secure alternatives:

| Secure Port | Service |
| ----------- | ------- |
| 443         | HTTPS   |
| 22          | SSH     |

---

# Secure Protocols

---

## HTTPS

Secure version of HTTP using SSL/TLS.

---

## SSH

Secure remote login protocol.

---

## SFTP

Secure file transfer protocol.

---

# Common Security Layers

---

## Physical Security

Protecting hardware.

---

## Network Security

Protecting data transmission.

---

## Application Security

Protecting software and applications.

---

# Cybersecurity Tools

Common tools used in network security:

* Wireshark
* Nmap
* Snort
* Suricata
* Burp Suite

---

# Security Best Practices

* Use firewalls
* Enable MFA
* Encrypt data
* Monitor traffic
* Disable unused ports
* Use secure protocols

---

# Cybersecurity Career Relevance

Network security is essential for roles like:

* SOC Analyst
* Penetration Tester
* Network Engineer
* Security Analyst
* Ethical Hacker

