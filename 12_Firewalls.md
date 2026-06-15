# Firewalls

## Description

This document explains Firewalls, one of the most important security controls used to protect networks and systems from unauthorized access. Firewalls monitor and control incoming and outgoing network traffic based on predefined security rules.

---

# What is a Firewall?

A firewall is a network security device or software that filters network traffic between trusted and untrusted networks.

It acts as a security barrier between:

```text
Internal Network
        ↕
     Firewall
        ↕
External Network (Internet)
```

---

# Why Firewalls are Important

Firewalls help organizations:

* Prevent unauthorized access
* Block malicious traffic
* Enforce security policies
* Protect sensitive data
* Monitor network activity

---

# How a Firewall Works

When network traffic reaches a firewall:

### Step 1

The firewall examines the packet.

### Step 2

It compares the packet against configured rules.

### Step 3

The firewall decides whether to:

```text
Allow
Block
Reject
Log
```

---

# Firewall Rule Example

Example Rule:

```text
Allow TCP Port 443
Block TCP Port 23
```

Result:

```text
HTTPS Allowed
Telnet Blocked
```

---

# Types of Firewalls

## 1. Packet Filtering Firewall

The oldest type of firewall.

Checks:

* Source IP
* Destination IP
* Protocol
* Port Number

Example:

```text
Source: 192.168.1.10
Destination: 8.8.8.8
Port: 443
```

Advantages:

* Fast
* Simple

Disadvantages:

* Limited visibility
* Basic security

---

## 2. Stateful Inspection Firewall

Tracks active network connections.

Monitors:

```text
Connection State
Session Information
```

Advantages:

* More secure than packet filtering
* Tracks established sessions

Disadvantages:

* Higher resource usage

---

## 3. Proxy Firewall

Acts as an intermediary between client and server.

Example:

```text
Client
   ↓
Proxy Firewall
   ↓
Server
```

Advantages:

* Hides internal systems
* Inspects application traffic

Disadvantages:

* Increased latency

---

## 4. Next-Generation Firewall (NGFW)

Modern firewall with advanced features.

Capabilities:

* Deep Packet Inspection (DPI)
* Application Awareness
* Intrusion Prevention System (IPS)
* Malware Detection
* SSL/TLS Inspection

Advantages:

* Advanced threat detection
* Better visibility

---

# Host-Based Firewall

Installed on an individual system.

Examples:

* Windows Defender Firewall
* UFW (Linux)
* pf (BSD)

Purpose:

```text
Protect a Single Device
```

---

# Network-Based Firewall

Protects an entire network.

Usually placed at:

```text
Network Edge
```

Purpose:

```text
Protect Multiple Systems
```

---

# Inbound and Outbound Traffic

## Inbound Traffic

Traffic entering a system.

Example:

```text
Internet → Computer
```

---

## Outbound Traffic

Traffic leaving a system.

Example:

```text
Computer → Internet
```

---

# Common Firewall Actions

## Allow

Permit traffic.

---

## Deny

Block traffic.

---

## Reject

Block traffic and notify the sender.

---

## Log

Record firewall activity.

---

# Firewall Rules

A firewall rule may contain:

```text
Source IP
Destination IP
Protocol
Port
Action
```

Example:

```text
Allow TCP 443
Block TCP 23
```

---

# Common Ports Controlled by Firewalls

| Port  | Service |
| ----- | ------- |
| 20/21 | FTP     |
| 22    | SSH     |
| 23    | Telnet  |
| 25    | SMTP    |
| 53    | DNS     |
| 80    | HTTP    |
| 110   | POP3    |
| 143   | IMAP    |
| 443   | HTTPS   |
| 445   | SMB     |
| 3389  | RDP     |

---

# Firewall Logging

Firewalls can record:

* Allowed Traffic
* Blocked Traffic
* Connection Attempts
* Security Events

Benefits:

* Auditing
* Incident Response
* Troubleshooting

---

# Linux Firewall Examples

## UFW

Check Status:

```bash
sudo ufw status
```

Enable Firewall:

```bash
sudo ufw enable
```

Allow SSH:

```bash
sudo ufw allow 22
```

Allow HTTPS:

```bash
sudo ufw allow 443
```

---

# Windows Firewall

View Firewall Status:

```powershell
Get-NetFirewallProfile
```

Windows Defender Firewall supports:

* Inbound Rules
* Outbound Rules
* Logging
* Application Control

---

# Firewall Placement

Typical Network Design:

```text
Internet
    ↓
Firewall
    ↓
Router
    ↓
Switch
    ↓
Devices
```

---

# Firewall Limitations

Firewalls cannot always stop:

* Insider Threats
* Social Engineering
* Phishing Attacks
* Malware from Trusted Sources

Firewalls should be combined with:

* Antivirus
* IDS/IPS
* Security Monitoring
* User Awareness Training

---

# Firewalls in Cyber Security

Firewalls are used for:

* Access Control
* Threat Prevention
* Traffic Monitoring
* Network Segmentation
* Compliance Requirements

