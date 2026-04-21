## 📌 Project Overview

This project demonstrates the implementation of a Web Application Firewall (SafeLine) to protect a vulnerable web application (DVWA). By positioning the WAF as a reverse proxy, I successfully mitigated several OWASP Top 10 vulnerabilities including SQL Injection, XSS, and Command Injection, while also implementing Rate Limiting to prevent HTTP Flooding.

## 🏗️ Architecture
The lab environment was built using a NAT Network in VirtualBox to simulate a real-world enterprise DMZ:
- Attacker: Kali Linux (Attacking via curl, ab, and Firefox).
- WAF (Reverse Proxy): SafeLine WAF running on Ubuntu Server.
- Victim App: Damn Vulnerable Web App (DVWA) hosted on the same Ubuntu server via Docker (Port 8080).
