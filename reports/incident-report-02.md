# Incident Report: Port Scan Detection

## Overview

This report documents a simulated port scanning attack detected within the lab environment using Splunk SIEM and UFW firewall logs.

The attack was launched from an external attacker machine and identified through analysis of repeated blocked connection attempts.

---

## Environment

- Attacker: Kali Linux (192.168.100.5)
- Target: Ubuntu Server (192.168.100.4)
- SIEM: Splunk Enterprise
- Firewall: UFW (Uncomplicated Firewall)

---

## Attack Details

- Attack Type: Port Scan (Reconnaissance)
- Tool Used: Nmap
- Scan Type: TCP SYN Scan

### Command Used

```
nmap -sS -p 1-1000 192.168.100.4
```

--- 

## Evidence

![nmap-attack](../assets/nmap-attack.png)

---

## Detection

The attack was detected by analyzing UFW firewall logs for repeated blocked connection attempts from a single source IP.

### Detection Query

```
index=network_logs "UFW BLOCK"
| rex "SRC=(?<src_ip>\d+.\d+.\d+.\d+)"
| stats count by src_ip
| where count > 50
```

---

## Findings

- Source IP: 192.168.100.5
- High volume of blocked connection attempts observed
- Multiple destination ports targeted
- Behavior consistent with reconnaissance activity

---

## Evidence

### Detection Output

![Detection](../assets/portscan-detection.png)

---

### Dashboard Visualization

![Dashboard](../assets/portscan-dashboard.png)

---

### Triggered Alert

![Alert](../assets/portscan-alert.png)

---

## Impact

- No successful access achieved
- Reconnaissance activity identified early
- Potential precursor to further attacks

---

## Response

- Firewall blocked incoming scan attempts
- SIEM detection rule identified abnormal behavior
- Alert triggered for SOC visibility
- Investigation performed using dashboard and log analysis

---

## Key Takeaways

- Port scanning can be detected through firewall logs
- Aggregation of blocked connections reveals attack patterns
- SIEM enables centralized monitoring and detection
- Early detection helps prevent further exploitation

---

## Conclusion

This incident demonstrates the effectiveness of firewall logging and SIEM-based detection in identifying reconnaissance activity in a controlled environment.
