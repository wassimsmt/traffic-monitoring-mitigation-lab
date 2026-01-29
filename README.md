# 📡 Traffic Monitoring & Mitigation Lab (Ubuntu Server)

## 🔎 Overview
This project demonstrates a hands-on cybersecurity lab focused on network traffic monitoring, threat detection, and mitigation techniques in a controlled environment. The lab simulates real-world attack scenarios such as port scanning and SSH brute-force attempts, followed by defensive measures using firewall rules and intrusion prevention tools.

The objective is to replicate a Security Operations Center (SOC) workflow: capture traffic, analyze indicators of compromise, correlate logs, and apply automated mitigation.

---

## 🎯 Objectives
- Capture baseline network traffic
- Detect suspicious activity (port scanning & SSH abuse)
- Analyze authentication logs
- Apply mitigation strategies
- Document evidence for incident response

---

## 🖥 Environment
- **Operating System:** Ubuntu Server
- **Role:** Monitored target
- **Interface:** enp0s3
- **Monitoring Tool:** tcpdump
- **Protected Service:** OpenSSH (Port 22)
- **Mitigation Tools:** UFW Firewall, Fail2ban
- **Attacker Machine:** Kali Linux

---

## 🧱 Lab Architecture
Attacker Device → Local Network → Ubuntu Server

---

## 🧪 Attack Simulation & Evidence

### 1️⃣ Baseline Traffic Capture
Purpose: Understand normal network behavior before attack simulation.

- Packet Capture: `pcaps/01_baseline.pcap`
- Summary Notes: `notes/01_baseline_summary.txt`

---

### 2️⃣ Port Scanning Simulation
Attack Method: 'nmap -sS -Pn -T3 <SERVER_IP>'

Detection Indicators:
- SYN packet bursts
- Unusual port probing behavior

Evidence:
- Capture File: `pcaps/02_scan.pcap`
- Analysis Notes: `notes/scan_syn_evidence.txt`

---

### 3️⃣ SSH Abuse Simulation
Attack Method:
Multiple failed SSH login attempts were generated to simulate brute-force behavior.

Detection:
- Monitored `/var/log/auth.log`
- Identified repeated authentication failures from a single source IP

Evidence:
- Packet Capture: `pcaps/03_ssh_abuse.pcap`
- Log Output: `logs/ssh_failed_passwords.txt`

---

## 🛡 Mitigation Measures

### Firewall Hardening
- Configured UFW rules
- Verified active filtering
- Evidence: `notes/ufw_status.txt`

### Intrusion Prevention
- Configured Fail2ban for SSH protection
- Automatic ban triggered after multiple failed attempts

Evidence:
- Fail2ban Configuration: `jail.d/sshd.local`
- Ban Proof: `notes/fail2ban_ban_proof.txt`

---

## 📊 Results
- Successfully detected port scanning behavior
- Correlated packet capture with authentication logs
- Identified attacker IP address
- Automatically blocked malicious activity using Fail2ban
- Demonstrated practical incident response workflow

---

## 🚀 Future Improvements
- Deploy Suricata IDS for real-time alerting
- Centralize logs using SIEM tools (Wazuh / Elastic Stack)
- Create dashboards for visual analysis
- Automate alert notifications

---

## 🧠 Skills Demonstrated
- Network traffic analysis
- Log correlation
- Threat detection
- Firewall configuration
- Incident response
- Defensive security practices

---

## 📌 Tools Used
- tcpdump
- Nmap
- UFW
- Fail2ban
- Linux system logs

---

## 👤 Author
Wassim Abelghouch — Cybersecurity Student & SOC Analyst Trainee
