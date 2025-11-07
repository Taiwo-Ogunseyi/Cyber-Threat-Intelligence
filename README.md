# Cyber-Threat-Intelligence

<h2>Description</h2>
- Malware Threat Intel Exercise - Research malware hashes from VirusTotal.
Trigger Wazuh threat intel integration. Report includes: Executive Summary, Technical Analysis, Detection/Correlation, Impact, Recommendations.
- Phishing Analysis Exercise - Analyze phishing emails (headers, links, attachments).
Identify IOCs and correlate with threat intel, Report includes: Executive Summary, IOCs, Technical Analysis, Attribution, Mitigation/User Awareness.
- OSINT Threat Intel Exercise - Investigate suspicious domains, IPs, or actors using OSINT tools (VirusTotal, Shodan, URLScan, MISP).
Enrich and analyze data for threat context. Report includes: Executive Summary, Methodology, Key Findings, Correlation (MITRE ATT&CK), Recommendations.<br/>

<h2>Languages and Utilities Used</h2>

- <b>Malware bazaar, </b>
  <b>VirusTotal, </b>
  <b>Wazuh, </b>
  <b>Hybrid Analysis, </b>
  <b>MixToolBox</b>
  <b>AbuseIPDB</b>
  <b>URL haus</b>
  <b>UrlScan.io</b>
  <b>MITRE ATT&CK Framework</b>

- <h2>Program walk-through:</h2>

- <h4> Phase 1: Simulation & Detection</h4>
Windows 10 Workstation - Perform repeated failed login attempts (6–8 times).

<p align="center">
Simulating Brute force attack on Windows 10 Workstation and its log capture in Event Viewer & Wazuh: <br/>
<img src="https://i.imgur.com/n3FVZPm.png" height="70%" width="70%" alt="network-setup" border="0">
<img src="https://i.imgur.com/FULq3Lo.png" height="70%" width="70%" alt="network-setup" border="0">
<img src="https://i.imgur.com/ODzzrzO.png" height="70%" width="70%" alt="network-setup" border="0">  
<br />
<br />

Ubuntu Server
<p align="center">
⚬ Run privilege escalation commands (sudo su,sudo -l).
<img src="https://i.imgur.com/FFxqXIf.png" height="70%" width="70%" alt="Screenshot-2025-07-31-215338" border="0">
<br />
<p align="center">
⚬ Create a suspicious user (sudo useradd hacker).
<img src="https://i.imgur.com/XZY69vF.png" height="70%" width="70%" alt="Screenshot-2025-07-31-215338" border="0">
<br />

- <h4> Phase 2: Network Activity & Capture</h4>

<p align="center">
⚬ Perform basic scanning and ping from kali to Windows
<img src="https://i.imgur.com/99tt1br.png" height="70%" width="70%" alt="Screenshot-2025-07-31-215338" border="0">
<img src="https://i.imgur.com/Z1rDqG5.png" height="70%" width="70%" alt="Screenshot-2025-07-31-215338" border="0">
<br />

<p align="center">
⚬ Perform basic scanning and ping from kali to Ubuntu.
<img src="https://i.imgur.com/1HhPjxW.png" height="70%" width="70%" alt="Screenshot-2025-07-31-215338" border="0">
<img src="https://i.imgur.com/MgW1KAt.png" height="70%" width="70%" alt="Screenshot-2025-07-31-215338" border="0">
<br />

- <h4> Phase 3: Mitigation </h4>
1. Propose Improvements
<p align="center">
⚬ Configure pfSense VLAN segmentation with at least two VLANs:
<img src="https://i.imgur.com/lattrvL.png" height="70%" width="70%" alt="Screenshot-2025-07-31-215338" border="0">
<br />

<p align="center">
￭ VLAN 1: Employee workstations (Windows).
<img src="https://i.imgur.com/iZu6Aoq.png" height="70%" width="70%" alt="Screenshot-2025-07-31-215338" border="0">
<img src="https://i.imgur.com/wFW4fhf.png" height="70%" width="70%" alt="Screenshot-2025-07-31-215338" border="0">
<br />
  
<p align="center">  
￭ Setting firewall rules for Windows Workstation VLAN
<img src="https://i.imgur.com/PnB3L39.png" height="70%" width="70%" alt="Screenshot-2025-07-31-215338" border="0">
<br />

<p align="center">  
￭ VLAN 2: Backend servers (Ubuntu).
<img src="https://i.imgur.com/SGhCLd8.png" height="70%" width="70%" alt="Screenshot-2025-07-31-215338" border="0">
<br />

<p align="center">  
⚬ Setting firewall rules for the DMZ VLAN
<img src="https://i.imgur.com/QYjdZ0W.png" height="70%" width="70%" alt="Screenshot-2025-07-31-215338" border="0">
<br />

</p>


