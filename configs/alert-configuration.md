# SSH Brute Force Alert Configuration

## Overview

This alert detects brute-force attacks by monitoring failed SSH login attempts within a defined time window.

---

## Detection Query

index="linux_logs" "Failed password for"
| rex "from (?<src_ip>\d+.\d+.\d+.\d+)"
| stats count by src_ip
| where count > 20

---

## Alert Configuration

- Type: Scheduled  
- Frequency: Every 5 minutes  
- Time Window: Last 15 minutes  
- Trigger Condition: Number of results > 0  

---

## Result

The alert successfully triggered when a brute-force attack was simulated from the attacker machine.

---

## Evidence

![Brute Force Alert](../assets/brute-force-alert.png)

---

## Key Insight

Automated alerting enables real-time detection of attacks, reducing response time in SOC environments.
