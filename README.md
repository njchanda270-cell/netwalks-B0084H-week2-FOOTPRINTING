# netwalks-B0084H-week2-FOOTPRINTING
Footprinting and Reconnaissance Report
Target: networkwalks.com
Target IP: 192.232.216.135
Internal Scope: 10.0.0.0/24
Pentester: Nathan Chanda

1. Executive Summary
This assessment performed passive and light active footprinting against networkwalks.com to determine what information an external attacker can gather without exploitation. The target is a WordPress site hosted on HostGator, protected by a ModSecurity WAF, but leaking significant technical detail through public DNS, HTTP headers, and WordPress itself.

No exploitation was performed. All findings below are from publicly available information.

2. Scope and Methodology
In Scope:   
networkwalks.com   Public DNS records   Public HTTP / HTTPS headers   Local network discovery on 10.0.0.0/24 for lab context   
Out of Scope:   
Exploitation, brute force, vulnerability scanning with payloads, denial of service   
Tools Used:   
Whois, WhatWeb, Nslookup, Curl -I, Wafw00f v2.4.2, DNSRecon, Zenmap / Nmap, Ipconfig

## 3. Findings - External Footprinting
   
### 3.1 Task 1: Whois - Domain Registration
![Whois](images/Whois.png)

### 3.2 Task 2: WhatWeb - Technology Fingerprinting
![WhatWeb](images/WhatWeb.png)

### 3.3 Task 3: Nslookup - DNS Resolution
![Nslookup](images/Nslookup.png)

### 3.4 Task 4: Curl -I - HTTP Headers
![Curl](images/Curl.png)

### 3.5 Task 5: Wafw00f - Web Application Firewall Detection
![Wafw00f](images/Wafw00f.png)

### 3.6 Task 6: DNSRecon - DNS Enumeration
![DNSRecon](images/DNSRecon.png)


## 4. Findings - Internal Network Discovery

### 4.1 Ipconfig - Local Configuration
![Ipconfig](images/lpconfig.png)

### 4.2 Zenmap - Network Scan
![Zenmap Hosts](images/ZenmapHosts.png)

*Note on MAC Addresses:* MAC addresses did not come up when the ping scan was run. Only IP addresses and host-up status were recorded. No MAC addresses were enumerated. This is expected behaviour for a ping scan, which uses ICMP Echo to determine host availability and does not perform ARP-based MAC resolution.


Conclusion

http://Networkwalks.com has basic protections in place: privacy protection, domain locking, SPF, and a ModSecurity WAF. However, an attacker can passively learn the exact hosting IP, web server, CMS version, plugin version, DNS software version, mail infrastructure, and API structure without sending a single malicious request.

Remediating DNSSEC and version disclosure will significantly reduce the attack surface.

This report contains only footprinting information gathered on 08 November 2026. No exploitation was attempted.

Submitted by:
Nathan Chanda
    
