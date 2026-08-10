# 🔐 Network Security Monitoring Project

## 📌 Project Overview
This project demonstrates real-time network traffic monitoring and attack detection using Suricata IDS and Wireshark in a controlled virtual lab environment.

The lab simulates multiple cyber attacks and analyzes how they are detected at the network level.

---

## 🏗️ Architecture
The project environment was built using a NAT Network in VirtualBox to simulate a real-world enterprise DMZ:
- Attacker: Kali Linux ( Attacking via firefox, burpsuite, nmap).
- Victim/Monitoring: Ubuntu ( monitoring via Suricata, Wireshark )
- Victim: Damn Vulnerable Web App (DVWA) hosted on the same Ubuntu server.

---

## ⚙️ Configuration & Setup
### 1. Lab Environment
The project was implemented in an isolated VirtualBox laboratory environment.
| Component |	Configuration |
| --------- | ------------- |
| Attacker |	Kali Linux 
| Victim / Monitoring |	Ubuntu
| IDS | Suricata |
| Packet Analysis |	Wireshark |
| Web Application |	DVWA |
| Network | VirtualBox NAT network |

### 2. VirtualBox Network Configuration

Both virtual machines were connected to an isolated VirtualBox network using NAT so that attack simulations could be performed in a controlled environment.

- Kali Linux  →  10.0.2.3
- Ubuntu      →  10.0.2.15

### 3. Suricata Configuration

```
alert http any any -> any any (msg:"SQLi Attempt Detected"; flow:to_server,established; http.uri; pcre:"/(\%27|'|--|%23|#|union(\s+all)?\s+select|(or|and)\s+\d+=\d+)/i"; classtype:web-application-attack; sid:1001001; rev:2;)
alert http any any -> any any (msg:"XSS Attempt Detected"; flow:to_server,established; http.uri; pcre:"/(<script.*?>.*?<\/script>|javascript:|onerror\s*=|onload\s*=|onclick\s*=|%3cscript%3e)/i"; classtype:web-application-attack; sid:1002001; rev:1;)
alert http any any -> any any (msg:"Login Failure Brute Force Detected"; flow:to_client,established; http.response_body; pcre:"/(invalid password|login failed|incorrect)/i"; detection_filter:track by_dst, count 10, seconds 60; sid:1002004; rev:1;)
```

### 4. Wireshark Configuration
Wireshark was installed on Ubuntu and configured to capture traffic from the same network interface monitored by Suricata.

During attack simulations:

- i. Start Wireshark.
- ii. Select the laboratory network interface.
- iii. Start packet capture.
- iv. Launch the attack from Kali.
- v. Stop the capture after the test.
- vi. Save the capture as a .pcapng file.

### 5. Web Application Setup
A deliberately vulnerable web application (DVWA) was deployed on the Ubuntu machine for controlled web-attack simulations.

The application was used to generate HTTP traffic for:

- XSS testing
- SQL injection testing
- Authentication attack testing

The vulnerable application was kept inside the isolated laboratory environment.

---

## ⚔️ Security Testing & Evidence
- ff

---

## 📊 Collected Evidence
- ff

---

## 🧠 Key Learnings
- Intrusion detection using Suricata
- Network traffic analysis
- Attack pattern recognition
- Packet-level investigation
