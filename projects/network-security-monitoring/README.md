# 🔐 Network Security Monitoring Project

## 📌 Project Overview
This project demonstrates real-time network traffic monitoring and attack detection using Suricata IDS and Wireshark in a controlled virtual lab environment.

The lab simulates multiple cyber attacks and analyzes how they are detected at the network level.

---

## 🏗️ Architecture
The project environment was built using a NAT Network in VirtualBox to simulate a real-world enterprise DMZ:
- Attacker: Kali Linux ( Attacking via firefox, burpsuite, 
- Victim : 

---

## 🎯 Objectives
- Monitor network traffic for suspicious activity
- Detect reconnaissance and malicious connections
- Analyze logs and correlate security events
- Create incident-ready documentation

---

## 🛠 Tools & Technologies
- Zeek (Network traffic analysis)
- Suricata (Network IDS)
- Wireshark (Packet analysis)
- Sysmon (Endpoint telemetry)
- Kali Linux (Attack simulation)
- Windows 10 (Victim machine)

---

## 🧪 Lab Environment
- Attacker: Kali Linux (VM)
- Victim: Windows 10
- Network Mode: Bridged / Internal Network
- Traffic Types:
  - Port scanning (Nmap)
  - HTTP requests
  - Suspicious outbound connections

---

## 🔍 Detection & Analysis
### Example Alerts & Logs
- Zeek `conn.log` – connection behavior analysis
- Suricata alerts – IDS signatures triggered
- Sysmon Event ID 3 – network connection telemetry

---

## 🧾 Findings
| Detection | Tool | Evidence |
|--------|------|---------|
| Port scan detected | Zeek | conn.log |
| Suspicious outbound HTTP | Sysmon | Event ID 3 |
| IDS alert triggered | Suricata | alert.log |

---

## 📊 Screenshots & Evidence
Screenshots showing:
- Alerts triggered
- Log analysis
- Traffic visualization

📂 Evidence stored in `/screenshots` and `/logs`

---

## 🚨 Incident Summary
- **Threat Type:** Network Reconnaissance
- **Severity:** Medium
- **MITRE ATT&CK:** TA0043 – Reconnaissance
- **Recommendation:** Block attacker IP, enable IDS alerting, continuous monitoring

---

## 📚 Skills Demonstrated
- Network traffic analysis
- Log correlation
- Incident investigation
- SOC documentation
- MITRE ATT&CK mapping

---

## ✅ Project Status
✔ Completed  
📅 Date: 2025

---

## 🔗 References
- MITRE ATT&CK
- Zeek Documentation
- Suricata Rules

