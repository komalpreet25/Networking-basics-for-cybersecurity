# ARP (Address Resolution Protocol)

## Description

ARP (Address Resolution Protocol) is a network protocol used to find the MAC Address of a device when its IP Address is known.

ARP operates within a Local Area Network (LAN) and is essential for communication between devices on the same network.

---

# Why ARP is Needed

Computers communicate using:

* IP Addresses (Logical Addresses)
* MAC Addresses (Physical Addresses)

When a device wants to send data to another device in the same network, it must know the destination MAC Address.

ARP helps discover that MAC Address.

---

# Example Scenario

Consider:

```text
PC A
IP: 192.168.1.10
MAC: AA-AA-AA-AA-AA-AA

PC B
IP: 192.168.1.20
MAC: BB-BB-BB-BB-BB-BB
```

PC A wants to send data to PC B.

PC A knows:

```text
192.168.1.20
```

But does not know:

```text
BB-BB-BB-BB-BB-BB
```

ARP is used to discover the MAC Address.

---

# How ARP Works

ARP follows a simple request-reply process.

---

## Step 1: ARP Request

PC A broadcasts:

```text
Who has 192.168.1.20?
Tell 192.168.1.10
```

Every device in the network receives this request.

---

## Step 2: ARP Reply

PC B responds:

```text
192.168.1.20 is at
BB-BB-BB-BB-BB-BB
```

---

## Step 3: Communication Starts

PC A stores the MAC Address and sends frames directly to PC B.

---

# ARP Communication Diagram

```text
PC A                           PC B

ARP Request
Who has 192.168.1.20?
------------------------>

ARP Reply
192.168.1.20 is at
BB-BB-BB-BB-BB-BB
<------------------------

Data Communication Begins
------------------------>
```

---

# ARP Cache

To avoid repeated ARP requests, devices maintain an ARP Cache.

The cache stores:

```text
IP Address → MAC Address
```

Example:

```text
192.168.1.1   → 00-AA-BB-CC-DD-11
192.168.1.20  → BB-BB-BB-BB-BB-BB
```

---

# Viewing ARP Cache

## Windows

```cmd
arp -a
```

---

## Linux

```bash
arp -a
```

or

```bash
ip neigh
```

---

# Sample Output

```text
192.168.1.1  at 00:11:22:33:44:55
192.168.1.20 at BB:BB:BB:BB:BB:BB
```

---

# Types of ARP

---

## 1. Dynamic ARP

Automatically created and updated.

Most commonly used.

---

## 2. Static ARP

Manually configured.

Does not expire automatically.

Example:

```bash
arp -s 192.168.1.20 BB-BB-BB-BB-BB-BB
```

---

# Gratuitous ARP

A device sends an ARP announcement about itself.

Used for:

* Detecting duplicate IP addresses
* Updating ARP tables
* High availability systems

Example:

```text
192.168.1.20 is at BB-BB-BB-BB-BB-BB
```

without being asked.

---

# Reverse ARP (RARP)

RARP was used to discover an IP Address using a MAC Address.

Example:

```text
MAC Known
IP Unknown
```

Today it is largely replaced by DHCP.

---

# ARP Packet Fields

Important ARP fields:

```text
Hardware Type
Protocol Type
Hardware Address Length
Protocol Address Length
Operation Code
Sender MAC Address
Sender IP Address
Target MAC Address
Target IP Address
```

---

# ARP and Ethernet

ARP works closely with Ethernet.

Ethernet frames require:

```text
Destination MAC
Source MAC
```

ARP provides the destination MAC.

---

# ARP and Routers

If the destination is outside the local network:

```text
PC → Router → Internet
```

The PC performs ARP for the router's MAC Address, not the remote device.

---

# ARP in Wireshark

Display only ARP packets:

```text
arp
```

---

# Typical ARP Request

```text
Who has 192.168.1.1?
Tell 192.168.1.10
```

---

# Typical ARP Reply

```text
192.168.1.1 is at
00:11:22:33:44:55
```

---

# Cybersecurity Importance of ARP

ARP is commonly abused by attackers.

Because ARP lacks authentication, devices trust ARP replies.

This creates security risks.

---

# ARP Spoofing

Also called:

```text
ARP Poisoning
```

An attacker sends fake ARP replies.

Example:

```text
Gateway IP → Attacker MAC
```

Victims believe the attacker is the router.

---

# ARP Spoofing Attack Flow

```text
Victim
   ↓
Attacker
   ↓
Router
```

The attacker intercepts network traffic.

---

# Risks of ARP Spoofing

* Man-in-the-Middle (MITM)
* Session Hijacking
* Credential Theft
* Traffic Manipulation
* Network Monitoring

---

# Detecting ARP Spoofing

Tools:

```text
Wireshark
arpwatch
XArp
IDS/IPS
```

Signs:

* Multiple MACs for one IP
* Frequent ARP replies
* Duplicate gateway entries

---

# Preventing ARP Attacks

### Static ARP Entries

Manually configure trusted mappings.

---

### Dynamic ARP Inspection (DAI)

Switch feature that validates ARP messages.

---

### Port Security

Restricts unauthorized devices.

---

### Network Segmentation

Limits attack spread.

---

### IDS/IPS Monitoring

Detects suspicious ARP behavior.

---

# ARP Related Commands

## Windows

```cmd
arp -a
```

View ARP table.

---

```cmd
arp -d *
```

Delete ARP cache.

---

## Linux

```bash
ip neigh
```

View ARP table.

---

```bash
ip neigh flush all
```

Clear ARP cache.

