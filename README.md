Sure! Here's a cleaned-up, more professional and readable version of your write-up. I kept your structure and technical details intact while improving clarity, grammar, and formatting.

---

# Traffic Analysis with Wireshark 1.0  
### Case Study: RedLine Stealer Infection

---

## 🛑 RedLine Stealer Overview

**RedLine Stealer** is a type of information-stealing malware that targets Windows systems. It is known for harvesting login credentials, browser data, cryptocurrency wallet information, and various sensitive user files.

The PCAP analyzed in this case contains malicious activity attributed to a **RedLine Stealer** infection that occurred in **July 2023**.

---

## 📋 Quiz Questions

1. What is the date and time in UTC the infection started?  
2. What is the IP address of the infected Windows client?  
3. What is the MAC address of the infected Windows client?  
4. What is the hostname of the infected Windows client?  
5. What is the user account name from the infected Windows host?  
6. What type of information did this RedLine Stealer try to steal?

---

## 🔍 PCAP Analysis

### Questions 1, 2 & 3: Infection Start Time, IP Address, and MAC Address

After applying basic web traffic filtering in Wireshark, the infection was traced to a single source IP: `10.7.10.47`.

- **Infection Start Time (UTC):** July 10, 2023, at 22:39 UTC  
- **IP Address:** 10.7.10.47  
- **MAC Address:** 80:86:5b:ab:1e:c4  

> ![Infection Info](https://imgur.com/5L4Orm2.png)

---

### Question 4: Hostname of the Infected Client

To determine the hostname, NetBIOS Name Service (NBNS) traffic was filtered in Wireshark.

- **Hostname:** DESKTOP-9PEA63H  

> ![Hostname](https://imgur.com/FJWxf0r.png)

---

### Question 5: User Account Name

By filtering for `kerberos.CNameString` fields, we identified the Windows user account.

- **User Account Name:** rwalters  

> ![User Info](https://imgur.com/sMnshNo.png)

---

### Question 6: Information Targeted by RedLine Stealer

#### 🔎 Analysis of Malicious Web Traffic

Initial web traffic filtering revealed **three unencrypted HTTP GET requests**. Following their TCP streams showed that one request used `WindowsPowerShell` as the **User-Agent**, suggesting a script was involved. Additionally, a **301 status code** indicated a redirect to a moved resource—another sign of malicious behavior.

> ![HTTP GET](https://imgur.com/IZQJeul.png)  
> ![User-Agent PowerShell](https://imgur.com/njNP3wD.png)

#### 📡 Targeted Data Exfiltration

To investigate what RedLine Stealer attempted to exfiltrate, this custom Wireshark filter was applied:

```
tcp.flags eq 0x0002 and !(tcp.port eq 443) and !(tcp.port eq 80) and !(ip.dst eq 10.7.10.0/24)
```

This filter isolates SYN packets initiating new TCP connections outside the local network and not on standard web ports. It revealed a connection attempt to:

- **IP:** 194.26.135.119  
- **Port:** 12432  

Following the TCP stream exposed the nature of the data RedLine was trying to steal.

---

### 🎯 Exfiltrated Data Types

- Files from the victim's **Desktop** and **Documents** folders  
- User data for **Chrome, Chromium, Edge, Opera, Vivaldi**, and other browsers  
- Cryptocurrency wallet data and browser extensions for wallets  
- **API keys** and **login credentials** from various applications  

> ![Stolen Data - 1](https://imgur.com/ZiWGEfy.png)  
> ![Stolen Data - 2](https://imgur.com/4jOXgc7.png)  
> ![Stolen Data - 3](https://imgur.com/m0STuiM.png)

---

Let me know if you want this turned into a PDF report or a markdown file!
