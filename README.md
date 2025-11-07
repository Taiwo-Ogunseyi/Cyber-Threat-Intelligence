# Cyber-Threat-Intelligence

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
A malware hash was gotten from Malware bazaar. The malware is a remote access trojan (RAT): 
<img src="https://i.imgur.com/zCOsZZQ.png" height="70%" width="70%" alt="network-setup" border="0"> <br/>

<p align="center">
A further research on the malware was done on Virustotal to confirm that it’s truly a malware: 
<img src="https://i.imgur.com/50GT7tS.png" height="70%" width="70%" alt="network-setup" border="0"> <br/>

<p align="center">
Additional information about the names and history of the malware is depicted in the screenshot below:
<img src="https://i.imgur.com/WSwSMNR.png" height="70%" width="70%" alt="network-setup" border="0"> <br/> 

<p align="center">
Wazuh threat intel was triggered on the Windows 10 workstation to identify the malware and alert the SOC Team. To achieve this, the hash of the malware was saved in a .txt file and dropped in the downloads folder on the Windows 10 workstation: 
<img src="https://i.imgur.com/ZarzhnW.png" height="70%" width="70%" alt="network-setup" border="0"> <br/>

<p align="center">
The malware saved as rat.txt was picked up in the downloads folder by the wazuh server and alert was triggered:
<img src="https://i.imgur.com/Pn6wX2Q.png" height="70%" width="70%" alt="network-setup" border="0"> <br/>

<p align="center">
Wazuh threat intel was triggered on the Ubuntu workstation to identify the malware and alert the SOC Team. To achieve this, the hash of the malware was saved in the ‘/root’ directory on the Ubuntu workstation: 
<img src="https://i.imgur.com/9s6idv7.png" height="70%" width="70%" alt="network-setup" border="0"> <br/>

<p align="center">
Wazuh threat intel was triggered on the Ubuntu workstation to identify the malware and alert the SOC Team. To achieve this, the hash of the malware was saved in the ‘/root’ directory on the Ubuntu workstation:
<img src="https://i.imgur.com/8lTKZYe.png" height="70%" width="70%" alt="network-setup" border="0"> <br/>

<p align="center">
The malware saved as Rat.txt was picked up in the ‘/root’ directory of Ubuntu workstation by the wazuh server and alert was triggered:
<img src="https://i.imgur.com/ESQ2eOn.png" height="70%" width="70%" alt="network-setup" border="0"> <br/>

<p align="center">
Hybrid-analysis was used to further prove that the malware was indeed malicious. The saved hash was upload on Hybrid-analysis and the analysis overview is presented in the screenshot below:
<img src="https://i.imgur.com/qDzwLwr.png" height="70%" width="70%" alt="network-setup" border="0"> <br/>
  
<br />
<br />

- <h4> Phase 2: Phishing Analysis Exercise</h4>
Analyze phishing emails (headers, links, attachments)

<p align="center">
⚬ The header information and content of a spam email was analyzed using mxtoolbox. The SPF and the DKIM of the email both failed as shown below <br/>
<img src="https://i.imgur.com/IfXzO9s.png" height="70%" width="70%" alt="Screenshot-2025-07-31-215338" border="0">
<br />

<p align="center">
⚬ Further analysis of the email’s header reveals the sender’s ip address, the send from, and the reply-to path. A closer look shows that the reply-to path and the send from emails are different.
<img src="https://i.imgur.com/aUpooZb.png" height="70%" width="70%" alt="Screenshot-2025-07-31-215338" border="0">
<br />

<p align="center">
⚬ The sender’s ip address was searched on ‘AbuseipDB’ and the result reveal that the ip address is malicious 
<img src="https://i.imgur.com/OzSGryR.png" height="70%" width="70%" alt="Screenshot-2025-07-31-215338" border="0">
<br />

<p align="center">
⚬ The sender’s ip address was searched on ‘AbuseipDB’ and the result reveal that the ip address is malicious
<img src="https://i.imgur.com/gvNsYSA.png" height="70%" width="70%" alt="Screenshot-2025-07-31-215338" border="0">
<br />

<p align="center">
⚬ The malicious email with its attachment was saved as a .eml file for further analysis. The Based64 code of the saved email was converted to hexadecimal as shown in the screenshot.
<img src="https://i.imgur.com/sS8QdHP.png" height="70%" width="70%" align="center" alt="Screenshot-2025-07-31-215338" border="0">
<br />

<p align="center">
⚬ Using HxD, the hexadecimal code was saved as a .png file to retrieve the malicious attachment in the email
<img src="https://i.imgur.com/2IHewbs.png" height="70%" width="70%" alt="Screenshot-2025-07-31-215338" border="0">
<br />
  
- <h4> Phase 3: OSINT Threat Intel Exercise </h4>
Investigate suspicious IPs or actors using OSINT tools.
<p align="center">
⚬ A suspicious domain was selected on url haus website:
<img src="https://i.imgur.com/7UnLnUK.png" height="70%" width="70%" alt="Screenshot-2025-07-31-215338" border="0">
<br />

<p align="center">
￭ The domain was checked on virustotal to confirm if it is malicious and the screenshot is presented below. 
<img src="https://i.imgur.com/8yp1xdN.png" height="70%" width="70%" alt="Screenshot-2025-07-31-215338" border="0">
<br />
  
<p align="center">  
￭ Urlscan was also used to scan the domain to see if it’s malicious as shown in the screenshot
<img src="https://i.imgur.com/XHGp913.png" height="70%" width="70%" alt="Screenshot-2025-07-31-215338" border="0">
<br />

<p align="center">  
￭ MITRE ATT&CK Framework.
<img src="https://i.imgur.com/FegssEX.png" height="70%" width="70%" alt="Screenshot-2025-07-31-215338" border="0">
<br />

</p>


