# TCP vs UDP

## Description

This document explains the differences between TCP (Transmission Control Protocol) and UDP (User Datagram Protocol). Both are transport layer protocols in the TCP/IP model and are responsible for communication between devices on a network.

---

# Transport Layer

TCP and UDP operate at the **Transport Layer** of the TCP/IP model.

Responsibilities:

* End-to-end communication
* Data transmission
* Error handling
* Port addressing
* Process-to-process communication

---

# What is TCP?

TCP stands for **Transmission Control Protocol**.

It is a connection-oriented protocol that ensures reliable communication between devices.

TCP guarantees:

* Data delivery
* Correct order of packets
* Error detection
* Retransmission of lost packets

---

# TCP Characteristics

### Connection-Oriented

A connection must be established before data transfer.

### Reliable

Lost packets are retransmitted.

### Ordered Delivery

Packets arrive in the correct sequence.

### Error Checking

Errors are detected and corrected.

### Slower

Additional reliability mechanisms increase overhead.

---

# TCP Three-Way Handshake

Before communication begins, TCP performs a handshake.

## Step 1: SYN

Client sends:

```text id="tcp1"
SYN
```

---

## Step 2: SYN-ACK

Server replies:

```text id="tcp2"
SYN-ACK
```

---

## Step 3: ACK

Client responds:

```text id="tcp3"
ACK
```

---

## Diagram

```text id="tcp4"
Client                Server

SYN     ------------>

         <----------- SYN-ACK

ACK     ------------>
```

Connection Established.

---

# TCP Termination

Connection closure uses:

```text id="tcp5"
FIN
ACK
```

to safely end communication.

---

# Common TCP Protocols

| Protocol | Port |
| -------- | ---- |
| HTTP     | 80   |
| HTTPS    | 443  |
| FTP      | 21   |
| SSH      | 22   |
| SMTP     | 25   |
| POP3     | 110  |
| IMAP     | 143  |

---

# What is UDP?

UDP stands for **User Datagram Protocol**.

It is a connectionless protocol that sends data without establishing a connection.

UDP focuses on speed rather than reliability.

---

# UDP Characteristics

### Connectionless

No handshake required.

### Faster

Less overhead than TCP.

### No Guaranteed Delivery

Packets may be lost.

### No Packet Ordering

Packets may arrive out of sequence.

### Lightweight

Uses fewer resources.

---

# UDP Communication

UDP simply sends packets.

```text id="udp1"
Sender
   ↓
Packets Sent
   ↓
Receiver
```

No acknowledgment is required.

---

# Common UDP Protocols

| Protocol | Port  |
| -------- | ----- |
| DNS      | 53    |
| DHCP     | 67/68 |
| TFTP     | 69    |
| SNMP     | 161   |
| NTP      | 123   |

---

# TCP Header Components

Common TCP fields:

```text id="tcp6"
Source Port
Destination Port
Sequence Number
Acknowledgment Number
Flags
Window Size
Checksum
```

---

# UDP Header Components

Common UDP fields:

```text id="udp2"
Source Port
Destination Port
Length
Checksum
```

UDP headers are much smaller than TCP headers.

---

# TCP vs UDP Comparison

| Feature         | TCP                           | UDP                    |
| --------------- | ----------------------------- | ---------------------- |
| Full Form       | Transmission Control Protocol | User Datagram Protocol |
| Connection      | Connection-Oriented           | Connectionless         |
| Reliability     | Reliable                      | Unreliable             |
| Speed           | Slower                        | Faster                 |
| Error Recovery  | Yes                           | No                     |
| Packet Ordering | Yes                           | No                     |
| Acknowledgments | Yes                           | No                     |
| Overhead        | Higher                        | Lower                  |
| Use Cases       | Web, Email, SSH               | Streaming, DNS, VoIP   |

---

# Real-World Examples

## TCP Examples

Used when reliability is important.

Examples:

```text id="tcp7"
Web Browsing
Online Banking
Email
File Transfers
SSH
```

---

## UDP Examples

Used when speed is important.

Examples:

```text id="udp3"
Video Streaming
Online Gaming
VoIP Calls
DNS Queries
Live Broadcasting
```

---

# TCP Advantages

* Reliable communication
* Error recovery
* Ordered delivery
* Data integrity

---

# TCP Disadvantages

* Higher overhead
* Increased latency
* More bandwidth usage

---

# UDP Advantages

* Fast communication
* Low latency
* Efficient for real-time applications
* Lower overhead

---

# UDP Disadvantages

* Packet loss possible
* No retransmission
* No delivery guarantee

---

# TCP and UDP in Wireshark

### Display TCP Traffic

```text id="ws1"
tcp
```

---

### Display UDP Traffic

```text id="ws2"
udp
```

---

# TCP and UDP in Nmap

### TCP Scan

```bash
nmap -sT target_ip
```

---

### SYN Scan

```bash
sudo nmap -sS target_ip
```

---

### UDP Scan

```bash
sudo nmap -sU target_ip
```

---

# Cyber Security Perspective

Security professionals analyze TCP and UDP traffic to:

* Detect attacks
* Identify services
* Investigate incidents
* Monitor networks
* Perform reconnaissance

Common attacks involve:

```text id="cyber1"
TCP Floods
UDP Floods
Port Scanning
Reflection Attacks
```

