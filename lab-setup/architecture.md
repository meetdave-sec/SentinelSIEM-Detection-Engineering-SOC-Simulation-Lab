# Lab Architecture

## Overview

This lab simulates a real-world Security Operations Center (SOC) environment where attack activities are generated, monitored, and analyzed using a SIEM.

The architecture is designed to demonstrate the full detection lifecycle from attack execution to alerting and investigation.

---

## Components

### Attacker Machine

- OS: Kali Linux
- IP Address: 192.168.100.5
- Purpose:
  - Launch attacks (Hydra, Nmap)
  - Simulate real-world attacker behavior

---

### Target Machine

- OS: Ubuntu Server
- IP Address: 192.168.100.4
- Services:
  - SSH (Port 22)
- Purpose:
  - Receive attacks
  - Generate logs for analysis

---

### SIEM System

- Tool: Splunk Enterprise
- Location: Installed on Ubuntu Server
- Purpose:
  - Ingest logs
  - Perform detection
  - Generate alerts
  - Provide dashboards for investigation

---

## Data Flow

1. Attacker (Kali) launches attack on target (Ubuntu)
2. Target system generates logs (auth.log, sys logs)
3. Splunk ingests logs from local system
4. Detection rules analyze logs
5. Dashboards visualize attack patterns
6. Alerts are triggered on suspicious activity

---

## Architecture Diagram (Conceptual)

```
Kali (Attacker)
        ↓
Ubuntu Server (Target)
   ├── auth.log
   ├── sys logs
        ↓
Splunk SIEM
   ├── Detection Rules
   ├── Dashboard
   ├── Alerts
```

---

## Key Insight

This architecture replicates a simplified SOC environment where logs are centralized, analyzed, and used for threat detection and response.
