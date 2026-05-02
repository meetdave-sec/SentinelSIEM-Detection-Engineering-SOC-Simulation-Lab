# Network Setup

## Overview

This document describes the network configuration used in the SentinelSIEM lab environment.

---

## Network Configuration

- Network Type: VirtualBox Host-Only Network
- Subnet: 192.168.100.0/24

---

## Machines

### Kali Linux (Attacker)

- IP Address: 192.168.100.5
- Role: Attack simulation
- Tools:
  - Hydra (brute force)
  - Nmap (port scanning)

---

### Ubuntu Server (Target + SIEM)

- IP Address: 192.168.100.4
- Role:
  - Target system
  - Log generator
  - SIEM host (Splunk)

---

## Connectivity Test

To verify connectivity:

From Kali:

```
ping 192.168.100.4
```

From Ubuntu:

```
ping 192.168.100.5
```

---

## Services

### SSH Service

- Port: 22
- Used for brute-force attack simulation

---

## Key Insight

A controlled virtual network allows safe simulation of attacks without impacting external systems, while enabling realistic traffic and log generation.
