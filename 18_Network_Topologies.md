# Network Topologies

## Description

A Network Topology refers to the physical or logical arrangement of devices and connections within a network.

It defines how computers, servers, switches, routers, and other network devices communicate with each other.

Understanding network topologies is important for designing, managing, troubleshooting, and securing networks.

---

# What is a Network Topology?

A topology describes:

* How devices are connected
* How data flows through the network
* Network structure
* Communication paths

---

# Types of Network Topologies

The most common network topologies are:

1. Bus Topology
2. Star Topology
3. Ring Topology
4. Mesh Topology
5. Tree Topology
6. Hybrid Topology

---

# 1. Bus Topology

In a Bus Topology, all devices share a single communication cable called the backbone cable.

---

## Diagram

```text
PC1 ---- PC2 ---- PC3 ---- PC4
         Shared Bus Cable
```

---

## How It Works

Data travels across the shared cable.

Every device receives the transmission, but only the intended recipient processes it.

---

## Advantages

* Easy to implement
* Low cost
* Requires less cable

---

## Disadvantages

* Single point of failure
* Difficult troubleshooting
* Performance decreases with more devices

---

## Real-World Usage

Historically used in early Ethernet networks.

Rarely used today.

---

# 2. Star Topology

Star Topology is the most common modern network design.

All devices connect to a central switch or hub.

---

## Diagram

```text
          PC1
           |
PC2 ---- Switch ---- PC3
           |
          PC4
```

---

## How It Works

All communication passes through the central switch.

---

## Advantages

* Easy management
* Easy troubleshooting
* Failure of one device does not affect others
* High performance

---

## Disadvantages

* Central device failure affects the network
* Requires more cabling

---

## Real-World Usage

* Offices
* Schools
* Data Centers
* Home Networks

---

# 3. Ring Topology

Devices are connected in a circular loop.

---

## Diagram

```text
PC1 ---- PC2
 |         |
PC4 ---- PC3
```

---

## How It Works

Data travels around the ring until it reaches the destination.

Some implementations use a token-passing mechanism.

---

## Advantages

* Predictable performance
* No collisions in token-based systems

---

## Disadvantages

* Failure of one device can impact the network
* Difficult maintenance

---

## Real-World Usage

Historically used in Token Ring networks.

Rare today.

---

# 4. Mesh Topology

In Mesh Topology, devices are interconnected with multiple paths.

---

## Diagram

```text
      PC1
     / | \
    /  |  \
  PC2--PC3
    \  | /
     \ |/
      PC4
```

---

## Types of Mesh

### Full Mesh

Every device connects directly to every other device.

---

### Partial Mesh

Only selected devices have multiple connections.

---

## Advantages

* High reliability
* Multiple communication paths
* Excellent fault tolerance

---

## Disadvantages

* Expensive
* Complex setup
* High cabling requirements

---

## Real-World Usage

* Enterprise Networks
* ISP Infrastructure
* WAN Environments

---

# 5. Tree Topology

Tree Topology combines multiple star networks into a hierarchical structure.

---

## Diagram

```text
             Core Switch
                  |
        -------------------
        |                 |
    Switch A         Switch B
      | |              | |
    PC1 PC2          PC3 PC4
```

---

## How It Works

Devices are organized into branches.

Communication flows through higher-level devices.

---

## Advantages

* Scalable
* Structured design
* Easy expansion

---

## Disadvantages

* Core device failure affects many systems
* More complex than star topology

---

## Real-World Usage

* Large Enterprises
* Universities
* Corporate Networks

---

# 6. Hybrid Topology

Hybrid Topology combines two or more topology types.

---

## Example

```text
Star + Mesh
Star + Bus
Tree + Mesh
```

---

## Advantages

* Flexible
* Scalable
* Supports complex environments

---

## Disadvantages

* Expensive
* Complex management

---

## Real-World Usage

Most modern enterprise networks use hybrid topologies.

---

# Physical vs Logical Topology

---

# Physical Topology

Shows actual device connections and cables.

Example:

```text
Switch
  |
PC1
```

---

# Logical Topology

Shows how data moves through the network.

May differ from physical topology.

---

# Topology Comparison Table

| Topology | Cost   | Reliability | Scalability | Complexity |
| -------- | ------ | ----------- | ----------- | ---------- |
| Bus      | Low    | Low         | Low         | Low        |
| Star     | Medium | High        | High        | Low        |
| Ring     | Medium | Medium      | Medium      | Medium     |
| Mesh     | High   | Very High   | Medium      | High       |
| Tree     | Medium | High        | High        | Medium     |
| Hybrid   | High   | High        | Very High   | High       |

---

# Network Topologies in Cyber Security

Understanding topology helps security professionals:

* Identify attack paths
* Design secure networks
* Place firewalls correctly
* Deploy IDS/IPS systems
* Segment networks

---

# Security Considerations

---

## Bus Topology

Risks:

* Shared traffic visibility
* Easy packet interception

---

## Star Topology

Risks:

* Central switch becomes critical target

---

## Mesh Topology

Benefits:

* High redundancy
* Better resilience during attacks

---

## Tree Topology

Requires strong access controls at higher-level devices.

---

# Topology and Network Devices

Common devices include:

```text
Switches
Routers
Firewalls
Access Points
Servers
```

Their placement depends on the chosen topology.

---

# Topology Selection Factors

When designing a network, consider:

* Cost
* Scalability
* Security
* Reliability
* Maintenance
* Performance

---

# Home Network Topology

Most home networks use:

```text
Star Topology
```

Example:

```text
Phone
Laptop
TV
Gaming Console
      |
   Router
```

---

# Enterprise Network Topology

Large organizations commonly use:

```text
Tree Topology
Hybrid Topology
```

to support many users and departments.

---

# Data Center Topology

Modern data centers often use:

```text
Leaf-Spine Architecture
Mesh Concepts
```

to provide redundancy and high performance.

