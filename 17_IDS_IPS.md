# IDS & IPS (Intrusion Detection System and Intrusion Prevention System)

## Description

IDS (Intrusion Detection System) and IPS (Intrusion Prevention System) are security technologies used to detect and respond to malicious activities in networks and systems.

They help organizations identify cyber attacks, policy violations, malware activity, and suspicious behavior.

IDS and IPS are important components of modern cybersecurity architecture.

---

# Why IDS and IPS Are Needed

Traditional firewalls mainly control traffic based on rules.

However, attackers may still:

* Exploit vulnerabilities
* Launch malware attacks
* Perform reconnaissance
* Use compromised accounts
* Conduct network attacks

IDS and IPS provide deeper inspection of network traffic and system activities.

---

# What is IDS?

IDS stands for:

```text
Intrusion Detection System
```

An IDS monitors traffic and generates alerts when suspicious activity is detected.

IDS does NOT automatically block attacks.

It only detects and reports them.

---

# IDS Workflow

```text
Network Traffic
       ↓
      IDS
       ↓
Attack Detected
       ↓
Alert Generated
```

---

# What is IPS?

IPS stands for:

```text
Intrusion Prevention System
```

An IPS monitors traffic and actively blocks malicious activity.

Unlike IDS, IPS can take action automatically.

---

# IPS Workflow

```text
Network Traffic
       ↓
      IPS
       ↓
Attack Detected
       ↓
Traffic Blocked
```

---

# IDS vs IPS

| Feature                             | IDS                        | IPS                         |
| ----------------------------------- | -------------------------- | --------------------------- |
| Full Form                           | Intrusion Detection System | Intrusion Prevention System |
| Detect Attacks                      | Yes                        | Yes                         |
| Generate Alerts                     | Yes                        | Yes                         |
| Block Attacks                       | No                         | Yes                         |
| Deployment                          | Passive                    | Inline                      |
| Risk of Blocking Legitimate Traffic | No                         | Possible                    |
| Performance Impact                  | Low                        | Higher                      |

---

# Types of IDS

There are two major IDS categories.

---

# 1. Network-Based IDS (NIDS)

Monitors network traffic.

Usually placed at strategic network locations.

---

## Example

```text
Internet
    ↓
Switch
    ↓
NIDS
    ↓
Internal Network
```

---

## Advantages

* Monitors multiple devices
* Centralized visibility
* Detects network attacks

---

# 2. Host-Based IDS (HIDS)

Installed directly on individual systems.

Monitors:

* Files
* Processes
* Logs
* System activity

---

## Example

```text
Server
   ↓
HIDS Agent
   ↓
Monitoring
```

---

## Advantages

* Detailed system monitoring
* Detects local attacks
* Monitors file integrity

---

# Types of IPS

---

# Network-Based IPS (NIPS)

Protects entire networks.

Inspects traffic before it reaches internal systems.

---

# Host-Based IPS (HIPS)

Installed on endpoints.

Protects individual systems from attacks.

---

# Detection Methods

IDS and IPS use multiple detection techniques.

---

# 1. Signature-Based Detection

Compares traffic against known attack signatures.

---

## Example

Known malware pattern:

```text
Attack Signature
      ↓
Traffic Match
      ↓
Alert
```

---

## Advantages

* Accurate
* Fast
* Low false positives

---

## Disadvantages

Cannot detect unknown attacks.

---

# 2. Anomaly-Based Detection

Detects unusual behavior compared to normal activity.

---

## Example

Normal Traffic:

```text
100 Requests/Minute
```

Suddenly:

```text
5000 Requests/Minute
```

System raises an alert.

---

## Advantages

Can detect unknown attacks.

---

## Disadvantages

Higher false positives.

---

# 3. Behavior-Based Detection

Monitors patterns and behaviors over time.

Examples:

* Privilege escalation
* Suspicious processes
* Abnormal system activity

---

# Common Attacks Detected

IDS and IPS can identify:

---

## Port Scanning

Example:

```text
Nmap Scan
```

Multiple ports probed quickly.

---

## Brute Force Attacks

Repeated login attempts.

---

## Malware Activity

Suspicious payloads and communication.

---

## DDoS Attacks

Large volumes of traffic targeting systems.

---

## Exploitation Attempts

Attempts to exploit software vulnerabilities.

---

## Command and Control Traffic

Malware communication with attackers.

---

# IDS/IPS Deployment Locations

Typical deployment:

```text
Internet
    ↓
Firewall
    ↓
IDS / IPS
    ↓
Internal Network
```

---

# Popular IDS/IPS Tools

---

# Snort

One of the most popular IDS/IPS solutions.

Features:

* Open Source
* Signature-Based Detection
* Real-Time Analysis
* Packet Inspection

---

# Suricata

Modern IDS/IPS engine.

Features:

* Multi-threaded
* High Performance
* Deep Packet Inspection
* Protocol Analysis

---

# Zeek (Bro)

Network monitoring and security analysis platform.

Features:

* Traffic Analysis
* Logging
* Threat Detection
* Network Visibility

---

# Security Onion

Linux distribution focused on network monitoring.

Includes:

* IDS
* IPS
* Log Analysis
* Threat Hunting Tools

---

# IDS Alerts Example

```text
[ALERT]
Possible Port Scan Detected
Source: 192.168.1.100
Target: 192.168.1.1
```

---

# IPS Response Example

```text
Attack Detected
Source Blocked
Connection Terminated
```

---

# False Positives

A false positive occurs when legitimate activity is incorrectly flagged as malicious.

Example:

```text
Normal User Activity
      ↓
Alert Generated
```

No actual attack exists.

---

# False Negatives

A false negative occurs when a real attack is missed.

Example:

```text
Attack Occurs
      ↓
No Alert Generated
```

Dangerous because attacks remain undetected.

---

# Advantages of IDS

* Threat visibility
* Security monitoring
* Incident detection
* Network awareness

---

# Advantages of IPS

* Real-time protection
* Automatic response
* Attack prevention
* Reduced manual intervention

---

# Limitations of IDS

* Cannot block attacks
* Alert fatigue
* Requires monitoring

---

# Limitations of IPS

* May block legitimate traffic
* Higher resource usage
* Requires tuning

---

# IDS and IPS in Cybersecurity

Security professionals use IDS and IPS for:

* Threat Detection
* Incident Response
* Network Monitoring
* Threat Hunting
* Compliance Requirements
* Security Operations Centers (SOC)

---

# IDS and Wireshark

Wireshark helps analysts investigate alerts generated by IDS and IPS solutions.

Example workflow:

```text
IDS Alert
      ↓
Wireshark Analysis
      ↓
Investigation
```

---

# IDS and Nmap

Port scans generated by:

```bash
nmap target_ip
```

can often trigger IDS alerts.

