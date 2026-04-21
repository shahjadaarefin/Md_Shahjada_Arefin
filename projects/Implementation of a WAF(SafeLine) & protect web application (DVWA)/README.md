# Implementation of a WAF(SafeLine) & protect web application (DVWA)

## 📌 Project Overview

This project demonstrates the implementation of a Web Application Firewall (SafeLine) to protect a vulnerable web application (DVWA). By positioning the WAF as a reverse proxy, I successfully mitigated several OWASP Top 10 vulnerabilities including SQL Injection, XSS, and Command Injection, while also implementing Rate Limiting to prevent HTTP Flooding.

## 🏗️ Architecture
The lab environment was built using a NAT Network in VirtualBox to simulate a real-world enterprise DMZ:
- Attacker: Kali Linux (Attacking via curl, ab, and Firefox).
- WAF (Reverse Proxy): SafeLine WAF running on Ubuntu Server.
- Victim App: Damn Vulnerable Web App (DVWA) hosted on the same Ubuntu server via Docker (Port 8080).

## 📊 Collected Evidence
Note: Screenshots of the following are located in the /images folder of this repo.
- Intercepted Page: The 403 Forbidden screen shown to the Kali attacker.
- Dashboard Logs: Real-time event logs showing the "SQL Injection" classification.
- Semantic Analysis Details: Detailed view of the WAF parsing the attack payload.

## 🧠 Key Learnings
- Reverse Proxy Logic: Configuring 000-default.conf and netplan to ensure proper traffic routing.
- WAF vs. Regex: Understanding how SafeLine uses intelligent parsing instead of simple word-matching to stop obfuscated attacks.
- SSL Termination: Deploying HTTPS at the edge (WAF) to inspect encrypted traffic before it reaches the web server.
