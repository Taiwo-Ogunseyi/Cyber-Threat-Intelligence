<img width="3980" height="105" alt="image" src="https://github.com/user-attachments/assets/c17860bb-0d5a-42be-ba91-29e24c4f199a" /># Cyber-Threat-Intelligence

<h2>Description</h2>
<p>- Malware Threat Intel Exercise - Research malware hashes from VirusTotal.
Trigger Wazuh threat intel integration. Report includes: Executive Summary, Technical Analysis, Detection/Correlation, Impact, Recommendations.</br></p>
<p>- Phishing Analysis Exercise - Analyze phishing emails (headers, links, attachments).
Identify IOCs and correlate with threat intel, Report includes: Executive Summary, IOCs, Technical Analysis, Attribution, Mitigation/User Awareness. </br></p>
- OSINT Threat Intel Exercise - Investigate suspicious domains, IPs, or actors using OSINT tools (VirusTotal, Shodan, URLScan, MISP).
Enrich and analyze data for threat context. Report includes: Executive Summary, Methodology, Key Findings, Correlation (MITRE ATT&CK), Recommendations.<br/>

<h2>Languages and Utilities Used</h2>

- <b>Malware bazaar, </b>
  <b>VirusTotal, </b>
  <b>Wazuh, </b>
  <b>Hybrid Analysis, </b>
  <b>MixToolBox, </b>
  <b>AbuseIPDB, </b>
  <b>URL haus, </b>
  <b>UrlScan.io, </b>
  <b>MITRE ATT&CK Framework</b>

- <h2>Program walk-through:</h2>

- <h4> Phase 1: Malware Threat Intel Exercise</h4>
Research malware hashes from VirusTotal

<p align="center">
A malware hash was gotten from Malware bazaar. The malware is a remote access trojan (RAT): <br/>
<img src="https://i.imgur.com/zCOsZZQ.png" height="70%" width="70%" alt="network-setup" border="0"> <br/>
A further research on the malware was done on Virustotal to confirm that it’s truly a malware: <br/>
<img src="https://i.imgur.com/50GT7tS.png" height="70%" width="70%" alt="network-setup" border="0"> <br/>
Additional information about the names and history of the malware is depicted in the screenshot below:<br/>
<img src="https://i.imgur.com/WSwSMNR.png" height="70%" width="70%" alt="network-setup" border="0"> <br/> 
Wazuh threat intel was triggered on the Windows 10 workstation to identify the malware and alert the SOC Team. To achieve this, the hash of the malware was saved in a .txt file and dropped in the downloads folder on the Windows 10 workstation: <br/>
<img src="https://i.imgur.com/ZarzhnW.png" height="70%" width="70%" alt="network-setup" border="0"> <br/>
The malware saved as rat.txt was picked up in the downloads folder by the wazuh server and alert was triggered: <br/>
<img src="https://i.imgur.com/Pn6wX2Q.png" height="70%" width="70%" alt="network-setup" border="0"> <br/>
Wazuh threat intel was triggered on the Ubuntu workstation to identify the malware and alert the SOC Team. To achieve this, the hash of the malware was saved in the ‘/root’ directory on the Ubuntu workstation: <br/>
<img src="https://i.imgur.com/9s6idv7.png" height="70%" width="70%" alt="network-setup" border="0"> <br/>
Wazuh threat intel was triggered on the Ubuntu workstation to identify the malware and alert the SOC Team. To achieve this, the hash of the malware was saved in the ‘/root’ directory on the Ubuntu workstation: <br/>
<img src="https://i.imgur.com/8lTKZYe.png" height="70%" width="70%" alt="network-setup" border="0"> <br/>
The malware saved as Rat.txt was picked up in the ‘/root’ directory of Ubuntu workstation by the wazuh server and alert was triggered: <br/>
<img src="https://i.imgur.com/ESQ2eOn.png" height="70%" width="70%" alt="network-setup" border="0"> <br/>
Hybrid-analysis was used to further prove that the malware was indeed malicious. The saved hash was upload on Hybrid-analysis and the analysis overview is presented in the screenshot below: <br/>
<img src="https://i.imgur.com/qDzwLwr.png" height="70%" width="70%" alt="network-setup" border="0"> <br/>
  
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


