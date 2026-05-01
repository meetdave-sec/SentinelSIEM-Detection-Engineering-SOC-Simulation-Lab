# SentinelSIEM – Detection Engineering & SOC Simulation Lab

## Overview

SentinelSIEM is a hands-on cybersecurity project that simulates a real-world Security Operations Center (SOC) using Splunk.

The project demonstrates the complete detection lifecycle:

Attack Simulation → Log Ingestion → Detection → Alerting → Investigation

---

## Lab Architecture

- Attacker: Kali Linux
- Target: Ubuntu Server
- SIEM: Splunk Enterprise
- Network: 192.168.100.0/24

---

## Scenario 1: SSH Brute Force Attack

### Attack

- Tool: Hydra
- Target: SSH service (Port 22)
- Result: Multiple failed login attempts

---

### Detection

- Log Source: `/var/log/auth.log`
- SIEM: Splunk
- Method: Regex-based field extraction + aggregation

---

### Alerting

- Threshold-based detection
- Scheduled alert triggered on suspicious activity

---

### Investigation

- IP analysis
- Target user identification
- Timeline visualization

---

### Dashboard

- Top attacker IPs
- Targeted users
- Attack timeline

---

## Key Skills Demonstrated

- SIEM (Splunk)
- Detection Engineering
- Log Analysis
- Incident Investigation
- Attack Simulation (Hydra, Nmap, Gobuster)
- Security Monitoring

---

## Project Structure

SentinelSIEM/
├── attacks/
├── detection-rules/
├── dashboards/
├── reports/
├── configs/
├── assets/
├── data-ingestion/
├── lab-setup/

---

## Outcome

This project demonstrates practical SOC analyst capabilities including attack detection, alerting, and investigation using real-world tools and techniques.

---

## Author

Meet Dave  
MSc Cyber Security – University of Surrey
