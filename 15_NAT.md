# NAT (Network Address Translation)

## Description

NAT (Network Address Translation) is a networking technique used to translate private IP addresses into public IP addresses and vice versa.

It allows multiple devices within a private network to access the internet using a single public IP address.

NAT is widely used in homes, offices, and enterprise networks.

---

# Why NAT is Needed

IPv4 addresses are limited.

There are billions of devices connected to the internet, but only a limited number of IPv4 addresses available.

NAT helps solve this problem by allowing many devices to share one public IP address.

---

# Example Without NAT

```text
PC 1 → Internet
PC 2 → Internet
PC 3 → Internet
```

Each device would need its own public IP address.

This would quickly exhaust available IPv4 addresses.

---

# Example With NAT

```text
PC 1
PC 2
PC 3
   ↓
Router (NAT)
   ↓
One Public IP
   ↓
Internet
```

All devices share a single public IP.

---

# Private IP Addresses

Private IP addresses are used inside local networks.

They are not routable on the public internet.

---

## Class A Private Range

```text
10.0.0.0 - 10.255.255.255
```

---

## Class B Private Range

```text
172.16.0.0 - 172.31.255.255
```

---

## Class C Private Range

```text
192.168.0.0 - 192.168.255.255
```

---

# Public IP Addresses

Public IP addresses are globally unique.

They are assigned by Internet Service Providers (ISPs).

Devices on the internet communicate using public IP addresses.

---

# How NAT Works

Suppose:

```text
PC IP:
192.168.1.10

Router Public IP:
49.35.20.100
```

When the PC accesses a website:

```text
Source:
192.168.1.10
```

The router changes it to:

```text
Source:
49.35.20.100
```

The website only sees the router's public IP.

---

# NAT Translation Process

```text
Private Device
192.168.1.10
      ↓
NAT Router
      ↓
49.35.20.100
      ↓
Internet
```

Responses return to the router, which forwards them to the correct device.

---

# NAT Table

The router maintains a NAT table.

Example:

| Private IP   | Public IP    |
| ------------ | ------------ |
| 192.168.1.10 | 49.35.20.100 |
| 192.168.1.20 | 49.35.20.100 |
| 192.168.1.30 | 49.35.20.100 |

---

# Types of NAT

There are three main types of NAT.

---

# 1. Static NAT

One private IP maps to one public IP.

---

## Example

```text
192.168.1.10
      ↔
49.35.20.100
```

Permanent mapping.

---

## Uses

* Web Servers
* Mail Servers
* Public Services

---

## Advantages

* Predictable mapping
* Easy server access

---

## Disadvantages

* Requires multiple public IPs

---

# 2. Dynamic NAT

Maps private IPs to a pool of public IPs.

---

## Example

```text
Private IP Pool

192.168.1.10
192.168.1.20
192.168.1.30

↓

Public Pool

49.35.20.100
49.35.20.101
49.35.20.102
```

Mappings are assigned dynamically.

---

## Advantages

* Efficient public IP usage

---

## Disadvantages

* Limited by available public IPs

---

# 3. PAT (Port Address Translation)

Also called:

```text
NAT Overload
```

Most common NAT type.

---

## Example

```text
192.168.1.10:5000
192.168.1.20:6000
192.168.1.30:7000

↓

49.35.20.100
```

Multiple devices share a single public IP using different port numbers.

---

## Why PAT is Popular

One public IP can support many devices simultaneously.

Used by most home routers.

---

# Static NAT vs Dynamic NAT vs PAT

| Feature               | Static NAT | Dynamic NAT  | PAT           |
| --------------------- | ---------- | ------------ | ------------- |
| Mapping               | One-to-One | Many-to-Many | Many-to-One   |
| Public IP Requirement | High       | Medium       | Low           |
| Common Usage          | Servers    | Enterprises  | Home Networks |
| Port Translation      | No         | No           | Yes           |

---

# NAT and Home Routers

Home routers perform PAT automatically.

Example:

```text
Laptop
Phone
Smart TV
Gaming Console
      ↓
Home Router
      ↓
Single Public IP
      ↓
Internet
```

---

# NAT and Port Forwarding

Port Forwarding allows external users to access internal services.

---

## Example

```text
Public IP:
49.35.20.100

Port:
80

↓

Forward To

192.168.1.50
```

Requests are redirected to the internal web server.

---

# Common Port Forwarding Uses

* Web Servers
* CCTV Systems
* Game Servers
* Remote Access Services

---

# NAT Advantages

### Conserves IPv4 Addresses

Reduces public IP consumption.

---

### Increased Security

Internal IP addresses are hidden.

---

### Cost Effective

Fewer public IPs required.

---

### Supports Large Networks

Many devices can share internet access.

---

# NAT Disadvantages

### Breaks End-to-End Connectivity

External devices cannot directly reach internal hosts.

---

### Protocol Issues

Some protocols struggle with NAT.

Examples:

```text
VoIP
IPSec
Peer-to-Peer Applications
```

---

### Additional Processing

Routers must maintain translation tables.

---

# NAT and IPv6

IPv6 provides a huge address space.

```text
340 undecillion addresses
```

Because of this, NAT is generally less necessary in IPv6 networks.

---

# NAT in Wireshark

When capturing traffic behind a router:

You may see:

```text
192.168.x.x
```

Inside the LAN.

Outside the router:

```text
Public IP Address
```

after NAT translation.

---

# NAT and Cyber Security

Security professionals encounter NAT regularly.

Used in:

* Firewalls
* VPNs
* Enterprise Networks
* Cloud Environments
* Home Networks

Understanding NAT helps during:

* Penetration Testing
* Network Troubleshooting
* Incident Response
* Log Analysis

---

# Common NAT Issues

### Double NAT

Occurs when two routers perform NAT.

Example:

```text
Router 1
      ↓
Router 2
      ↓
Internet
```

Can cause gaming and connectivity issues.

---

### Incorrect Port Forwarding

Services become inaccessible.

---

### NAT Table Exhaustion

Large traffic volumes may overload the translation table.

---

# Common Commands

## Windows

Display IP configuration:

```cmd
ipconfig
```

---

## Linux

```bash
ip a
```

---

## Linux NAT Rules

View NAT rules:

```bash
sudo iptables -t nat -L
```

