Home SOC Lab — Threat Detection & Incident Response

1. Project Overview
A fully functional home Security Operations Centre (SOC) 
built using free open-source tools to simulate real-world 
threat detection and incident response workflows used in 
Australian cybersecurity operations.

2. Lab Architecture

| Machine | OS | IP | Role |
|---|---|---|---|
| Wazuh-SIEM | Ubuntu 26.04 | 192.168.56.101 | SIEM & Log Analysis |
| Windows-Victim | Windows 10 | 192.168.56.20 | Monitored Endpoint |
| Kali-Attacker | Kali Linux | 192.168.56.103 | Attack Simulation |

3. Tools Used
- Wazuh 4.7.5 — SIEM and security monitoring
- VirtualBox — virtualisation platform
- Kali Linux — attack simulation
- Metasploit Framework — exploitation framework
- Nmap — network reconnaissance
- Windows Event Logging — endpoint telemetry

4. Attacks Simulated

### Attack 1 — Network Reconnaissance (Nmap)
- Tool: Nmap 7.98
- Target: 192.168.56.20 (Windows endpoint)
- Ports discovered: 135 (RPC), 139 (NetBIOS), 445 (SMB)
- MITRE ATT&CK: T1046 — Network Service Scanning
- Detection: Wazuh network connection alerts

### Attack 2 — SMB Brute Force (Metasploit)
- Tool: Metasploit smb_login module
- Target: administrator account via port 445
- Result: 11 authentication failures, account lockout triggered
- MITRE ATT&CK: T1110.001 — Password Guessing
- Detection: Wazuh Rule 60122 fired — level 10 HIGH alert

### Attack 3 — EternalBlue Vulnerability Check
- Tool: Metasploit ms17_010_eternalblue
- Target: 192.168.56.20
- Result: NOT VULNERABLE — system is patched
- MITRE ATT&CK: T1210 — Exploitation of Remote Services
- Finding: Endpoint protected against CVE-2017-0144

4.  Key Findings
- Wazuh successfully detected all attack attempts in real time
- Authentication failure alerts fired within seconds of attack start
- MITRE ATT&CK framework automatically mapped by Wazuh
- Account lockout policy triggered as expected
- No successful unauthorised access achieved

5.  Incident Reports
- IR-2026-001: SMB Brute Force Attack (see /reports folder)

6.  Skills Demonstrated
- SIEM deployment and configuration
- Windows endpoint monitoring with Wazuh agent
- Real-time alert triage and analysis
- MITRE ATT&CK framework mapping
- Incident response documentation
- Network reconnaissance techniques
- Vulnerability assessment
- Log analysis and forensic investigation

7. Framework Alignment
This project demonstrates practical skills aligned with:
- ASD Essential Eight (Australian Signals Directorate)
- MITRE ATT&CK Framework
- NIST Cybersecurity Framework

8. Author
Muhammad Zoraiz Umar
Master of Computer Science (Cybersecurity & Machine Learning)
University of Wollongong
LinkedIn: https://www.linkedin.com/in/muhammadzoraizumar/