## 📌  ** Project Overview **

This project demonstrates the implementation of a Security Information and Event Management (SIEM) system using Wazuh in a virtualized lab environment. The setup simulates real-world cyberattacks and monitors system activities such as SSH login attempts and file integrity changes.

The lab includes an attacker machine (Kali Linux), a victim/blue team machine (Ubuntu), and a Wazuh SIEM server running on VirtualBox.

## 🖥️ Lab Environment
| Component | Description |
| Attacker | Kali Linux |
| Victim / Blue Team | Ubuntu 24.04 LTS |
| SIEM Platform | Wazuh v4.14.2 |
| Virtualization | VirtualBox |

## 🎯 Project Objectives
- Deploy and configure Wazuh SIEM
- Monitor SSH authentication logs
- Track file creation, deletion, and modification
- Detect security incidents
- Map events to MITRE ATT&CK framework
- Practice real-world SOC monitoring skills

## ⚙️ System Architecture
- Kali Linux performs simulated attacks.
- Ubuntu system generates security and file activity logs.
- Wazuh agent collects logs and monitors file integrity.
- Logs are forwarded to the Wazuh server.
- Wazuh analyzes events and generates alerts.
- Security incidents are visualized in the Wazuh dashboard.

## 📂 Log Collection Configuration
The following Wazuh configuration was used to collect system and file integrity logs:

<localfile>
  <log_format>syslog</log_format>
  <location>/var/log/auth.log</location>
</localfile>

<directories realtime="yes" report_changes="yes" check_all="yes">
  /home/hridoy/Desktop/wazuh
</directories>

## Monitored Activities
SSH login attempts (/var/log/auth.log)
File creation and deletion
File modification
Directory changes in real-time

## 🧪 Attack Simulation
Performed SSH brute-force attacks from Kali Linux
Created and deleted files on Ubuntu
Modified monitored directories
Tested SIEM alert generation
Example command:
touch who.txt

## 📊 Key Features
✅ Real-time File Integrity Monitoring
✅ SSH Authentication Monitoring
✅ Centralized Log Management
✅ MITRE ATT&CK Mapping
✅ Incident Detection & Analysis
✅ Endpoint Visibility

## 📈 Dashboard & Analysis
The Wazuh dashboard was used to:
Monitor endpoint status
View security alerts
Analyze MITRE ATT&CK techniques
Track compliance metrics
Investigate incidents
Detected techniques included:
Credential Access (T1110)
Privilege Escalation (T1548)
Defense Evasion (T1078)
Impact (T1070)

## 🛠️ Skills Demonstrated
SIEM Deployment & Management
Log Analysis & Correlation
Threat Detection
Linux Security Monitoring
Incident Response
SOC Operations
MITRE ATT&CK Framework

## 🚀 Future Improvements
Integrate ELK Stack
Add more attack scenarios
Automate incident response
Create custom detection rules
Implement email/SIEM alerts

## 📚 Learning Outcome
This project enhanced my practical skills in:
Building SOC labs
Monitoring endpoints
Analyzing security events
Investigating cyber threats
Using enterprise-level SIEM tools
