# **Wireshark Traffic Analysis Case Studies**

## 📖 Overview
This repository contains a growing collection of **traffic analysis projects** conducted with **Wireshark**.  
Each case study simulates the workflow of a **SOC analyst**, investigating real-world style malware infections and answering key incident response questions such as:  

- Which host in the network was infected?  
- What was the source of the infection?  
- Which domains and IPs were contacted?  
- What artifacts or payloads were observed?  
- What Indicators of Compromise (IOCs) can be extracted?  

These investigations are designed to strengthen skills in **PCAP analysis, malware traffic detection, and forensic reporting**.

---

## 🧪 Projects Included

### 1. **Traffic Analysis with Wireshark 1.0 – RedLine Stealer Infection**  
Analyzed a PCAP containing **RedLine Stealer**, an infostealer known for exfiltrating browser data, credentials, and cryptocurrency wallet information.  
- Identified infected host (IP, MAC, Hostname, User).  
- Observed malicious HTTP traffic and PowerShell activity.  
- Confirmed exfiltration attempts to an external C2 server.  
- Extracted data types targeted by RedLine Stealer.  

📄 [Read Full Case Study](./Lab1-RedLine%20Stealer%20Infection/README.md)

---

### 2. **Traffic Analysis with Wireshark 2.0 – Fake Google Authenticator Infection**  
Investigated a case where a user downloaded a **malicious fake Google Authenticator application**.  
- Identified infected host details (IP, MAC, Hostname, User).  
- Uncovered typo-squatted domain `authenticatoor.org`.  
- Revealed active C2 servers (`82.221.136.26`, `104.21.64.1`).  
- Analyzed VBScript & obfuscated PowerShell payload execution.  
- Confirmed IOCs via VirusTotal.  

📄 [Read Full Case Study](./Lab2-Fake%20Google%20Authenticator%20Infection/README.md)

---

## 🚀 Future Additions
More case studies will be added to this repository, covering different malware families, network attack types, and traffic analysis techniques. Stay tuned for:  
- Ransomware traffic analysis  
- Phishing case investigations  
- Advanced persistence mechanisms in malware  

---

## ✅ Key Takeaways
- **Wireshark** is a powerful tool for reconstructing malware infections.  
- Careful traffic filtering and endpoint analysis can expose hidden attacker activity.  
- Documenting case studies helps build strong analytical workflows for SOC environments.  
