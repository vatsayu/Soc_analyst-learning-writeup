## Intrusion Detection System (IDS)
- An IDS is hardware or software used to detect security attacks by monitoring a network or host.
### Types of IDS
- Network Intrusion Detection System (NIDS)
- Host Intrusion Detection System (HIDS)
- Protocol-based Intrusion Detection System (PIDS)
- Application Protocol-based Intrusion Detection Systems (APIDS)
- Hybrid Intrusion Detection System - Combinations of two or more violation detection approaches.
### Examples
- Zeek/Bro
- Snort
- Suricata
- Fail2Ban
- OSSEC
### Physical Location of IDS Device
- May vary depending on type of IDS.
	- I.e., A NIDS should be positioned closer to network devices that provide access to external network. A HIDS should be positioned close to host in network.

#### Q1: How many of the following are tools in the IDS type?  
1. Snort  
2. Volatility  
3. OllyDbg  
4. Suricata  
5. Zeek/Bro  
6. REMnux  
  
**Answer Format:** X  
  
**Sample Answer:** 7
```
3
```
Snort, Zeek/Bro, and Suricata are IDS tools.

#### Q2: According to the Snort IDS log, what is the IP address from which the response came?  

![](https://ld-images-2.s3.us-east-2.amazonaws.com/Security+Solutions/question-2.png)

**Answer Format:** X.X.X.X  
  
**Sample Answer:** 192.168.1.100
```
DNS
```
DNS uses port 53.

**NOTE:** You can use the machine to solve the questions from the hands-on section above.
#### Q4: What is the HTTP request method according to the given Zeek IDS HTTP log?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\zeek-http.log.zip  
  
**Answer Format:** METHOD  
  
**Sample Answer:** HEAD
```
GET
```

#### Q5: What is the FTP command used for file transfer according to the given Zeek IDS FTP log?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\zeek-ftp.log.zip  
  
**Answer Format:** XXXX  
  
**Sample Answer:** LIST
```
RETR
```
`RETR` is a FTP command used for file transfer.

## Intrusion Prevention System (IPS)
- An IPS is hardware or software that detects and prevents security violations.
### Types of IPS
- Network-based intrusion prevention system (NIPS)
- Host-based intrusion prevention system (HIPS)
- Network behavior analysis (NBA)
- Wireless intrusion prevention system (WIPS)
### Examples
- Cisco NGIPS
- Suricata
- Fidelis
### Log Resources
- Date/Time Info
- Message about attack
- Source IP
- Source Port
- Destination IP
- Destination Port
- Action info
- Device Name
### Physical Location of IPS Device
- Varies depending on IPS type.

**NOTE:** You can use the machine to solve the questions from the hands-on section above.

#### Q1: According to the given Suricata IPS log, has the command been run successfully?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\suricata1.log.zip  
  
**Answer Format:** Y/N
```
Y
```
Yes, as noted by `Successful User Privilege Gain`.

#### Q2: What is the name of the SSL vulnerability that is attempted to be exploited in the given Suricata IPS log?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\suricata2.log.zip
```
POODLE
```
`ET POLICY SSLv3 inbound connection to server vulnerable to POODLE attack`

#### Q3: What is the name of the scanning tool that triggers the creation of the given Suricata IPS log?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\suricata3.log.zip
```
Nmap
```
`ET SCAN Possible Nmap User-Agent Observed`

## Firewall
- Firewall is a security software or hardware that monitors incoming/outgoing network traffic according to rules it contains (allows or denies packets).
### Types of Firewalls
1. Application-level Gateways (Proxy Firewalls)
	- Functions at application-layer (OSI).
2. Circuit-level Gateways
	- Easily configurable.
	- Low resource consumption.
	- Simplified structure.
	- Verify TCP connections and sessions (session layer of OSI).
3. Cloud Firewalls
	- No physical resources.
	- Easily reconfigured based on demand or traffic load.
4. Endpoint Firewalls
5. Network Address Translation (NAT) Firewalls
6. Next-generation Firewalls (NGFW)
	- Combines features of different firewalls.
	- Deep packet inspection (DPI).
	- Block external threats, malware attacks, and advanced attacks.
7. Packet-filtering Firewalls
8. Stateful Multi-layer Inspection (SMLI) Firewalls
	- Capable of packet inspection and TCP handshake verification.
	- Track status of established connections.
9. Threat-focused NGFW
	- Has advanced threat detection features.
	- React quickly to attacks.
	- Shorten time from when attack first detected to cleaning phase.
10. Unified Threat Management (UTM) Firewalls
	- Special type of stateful inspection firewalls with antivirus and intrusion prevention.
### How Firewall Works
- Creates safety barrier between private network and public Internet.
- Incoming packets are allowed or blocked depending on firewall rules.
### Examples
- Fortinet
- Palo Alto Networks
- SonicWall
- Checkpoint
- Juniper
- pfsense
- Sophos
### Log Resources
- Date/Time Info
- Source IP
- Destination IP
- Source Port
- Destination Port
- Action Info
- Number of Packets Sent/Received
### Physical Location of Firewall Devices
- Varies depending on firewall type.
	- I.e., a host-based firewall is placed in front of host.

**NOTE:** You can use the machine to solve the questions from the hands-on section above.

#### Q1: What is the action taken according to the given firewall log?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\firewall.log.zip
```
deny
```

#### Q2: What is the source IP address according to the given firewall log?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\firewall.log.zip  
  
**Answer Format:** X.X.X.X  
  
**Sample Answer:** 192.168.1.100
```
192.168.68.12
```

#### Q3: What is the destination port number according to the given firewall log?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\firewall.log.zip  
  
**Answer Format:** XXX  
  
**Sample Answer:** 111
```
143
```

#### Q4: According to the given Windows Defender Firewall log, what is the IP address that sends the TCP segment whose source port is 5421?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\pfirewall.log.zip  
  
**Answer Format:** X.X.X.X  
  
**Sample Answer:** 192.168.1.100
```
192.168.1.9
```

#### Q5: According to the given Windows Defender Firewall log, which network protocol do the logs associated with the "8.8.8.8" IP address belong to?  
  
**Note:** Enter the abbreviation of the Protocol name.  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\pfirewall.log.zip  
  
**Answer Format:** XXXX  
  
**Sample Answer:** DHCP
```
ICMP
```

## Endpoint Detection and Response (EDR)
- An EDR is a security product installed on endpoint devices.
- Constantly monitors activities in systems for ransomware & malware, and takes action against malicious activities.
### EDR Core Components
- Endpoint data collection agents.
- Automated response.
- Analysis and forensics.
### Functions of EDR
1. Monitor and collect each process on device that may identify a security threat.
2. Analyze behavior of threat actor according to data collected.
3. Inform relevant analyst to take appropriate security action.
4. Allow forensic analysis.
### Examples
- SentinelOne
- CrowdStrike
- CarbonBlack
- Palo Alto
- FireEye HX

**NOTE:** You can use the machine to solve the questions from the hands-on section above.
#### Q1: What is the name of the powershell script that is tried to be downloaded according to the given Crowdstrike EDR log?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\edr1.log.zip  
  
**Answer Format:** XX-XX
```
Invoke-Mimikatz
```

#### Q2: According to the given Crowdstrike EDR log, what is the name of the MITRE technique used by the attacker?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\edr1.log.zip  
  
**Answer Format:** XXX XXX XXX
```
OS Credential Dumping
```

#### Q3: According to the given Crowdstrike EDR log, what is the name and extension of the file that the attacker is trying to download onto the system?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\edr2.log.zip  
  
**Answer Format:** XX-XX.XX
```
Get-System.ps1
```

#### Q4: What is the severity of the alert based on the given Crowdstrike EDR log?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\edr2.log.zip
```
High
```

## Antivirus Software (AV)
- Antivirus Software (AV) is security software that detects and blocks malware from system.
### Types of Antivirus Software
- Signature-Based Scanning
	- Detect malware with a digital signature.
	- Digital signatures are kept in database and must constantly be updated.
- Heuristic Scanning
	- Monitors the accesses and behaviors of examined file.
### Examples
- McAfee
- Symantec
- BitDefender
- Eset
- Norton
### Log Sources
- Size of file
- Name of file
- Signature
- Type of malware

**NOTE:** You can use the machine to solve the questions from the hands-on section above.

#### Q1: **Question:** According to the given Windows Defender log, what is the type of malware named “executable.8180.exe”?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\win-defender.log.zip
```
Trojan
```

#### Q2: According to the given Windows Defender log, what is the name of the file belonging to the "Backdoor" type malware?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\win-defender.log.zip
```
program1
```

## Sandbox Solutions
- Sandbox is a technology used to run/open executable files (known to be as malware) in an isolated environment.
### Benefits
- Does not put hosts and operating systems at risk.
- Detects dangerous files.
- Allows testing of software updates.
- Defend against 0-day vulnerabilities.
### Examples
- Checkpoint
- McAfee
- Symantec
- Trend Micro
- Proofpoint

#### Q1: According to the sandbox analysis result in the URL given below, for which domain address was the DNS request made?  
    yser0
**URL:** [https://app.any.run/tasks/2d2ca664-521c-48bf-9748-722cbf34bcea/](https://app.any.run/tasks/2d2ca664-521c-48bf-9748-722cbf34bcea/)  
  
**SHA256 Hash:** 4a24048f81afbe9fb62e7a6a49adbd1faf41f266b5f9feecdceb567aec096784  
  
**Answer Format:** www.XXX...XXX.com
```
www.xmlformats.com
```

#### Q2: What is the name and extension of the file that performs the malicious activity on the system according to the sandbox analysis result in the URL given below?  
  
**URL:** [https://app.any.run/tasks/73db6760-6ca1-42fc-bd8d-dd6425d7acea](https://app.any.run/tasks/73db6760-6ca1-42fc-bd8d-dd6425d7acea)  
  
**SHA256 Hash:** dcbd77ad65145ab5aa64b8c08608991a6cc23daabf02cf0695f2261da3ec5b7d  
  
**Sample Answer:** malwr.exe
```
DotSetupSDK.dll
```
I swear there were other possible answers but this is the one LetsDefend was looking for. `DotSetupSDK.dll` is a potentially unwanted program that is installed when executing `MEmu-setup-abroad-sdk.exe`
I looked into the files tab on the AnyRun analysis and noticed a couple of executables were not malicious (based on VirusTotal scans).

## Data Los Prevention (DLP)
- DLP prevents exfiltration of sensitive and critical information.
### Types of DLP
- Network DLP - Responsible for taking security actions on network (i.e., block connections attempting to upload to FTP server).
- Endpoint DLP - Monitors on particular device instead of network.
- Cloud DLP - Prevents leakage over cloud.
### How does DLP work?
- Detects according to the rules configured.
	- i.e., If there is a credit card number in email, it will take relevant action - encryption.
### Examples
- Forcepoint
- McAfee
- Trend Micro
- Checkpoint
- Symantec

## Asset Management Solutions
- Monitor operating status of assets, maintaining them, and removing them when necessary.
### Benefits
- Facilitates standards.
- Documentation.
- Improves working performance of assets.
- Inventory control.
- Strategic decision-making support.
### Types and Components of IT Asset Management
1. Software
2. Hardware
3. Mobile devices
4. The Cloud
### Examples
- AssetExplorer
- Ivanti
- Armis
- Asset Panda

## Web Application Firewall (WAF)
- WAF is a security software/hardware that monitors, filters, and blocks incoming/outgoing packets to a web application.
- Typically placed in front of web applications.
### Types of WAF
1. Network-based WAF
2. Host-based WAF
3. Cloud-based WAF
### How does a web application firewall (WAF) work?
- Manages inbound traffic according to rules configured on it.
	- Allowed/blocked.
### Examples
- AWS
- Cloudflare
- F5
- Citrix
- Fortiweb

**NOTE:** You can use the machine to solve the questions from the hands-on section above.

#### Q1: According to the given AWS WAF log, a request for SQL_Injection attack was blocked. What is the IP Address that sent this request?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\aws-waf.log.zip  
  
**Answer Format:** X.X.X.X  
  
**Sample Answer:** 192.168.1.100
```
185.220.101.35
```

#### Q2: According to the given Cloudflare WAF log, an HTTP request was sent to the IP address 185.220.102.244 . Which HTTP method does this HTTP request use?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\cloudflare-waf.log.zip
```
GET
```

## Load Balancer
- A load balancer is hardware/software used to distribute traffic to servers.
	- Prevents overloading - delays and loss of access.
- Usually placed in front of servers.
### Benefits of Load Balancers
1. Efficiency
2. Flexibility
3. Reduced Downtime
4. Redundancy
5. Scalable
### Logic Behind How Load Balancer Operators
- Uses some mathematical algorithm to perform load balance.
### The Importance of Load Balancer for Security
- **DoS (Denial of Service)**: Send more network traffic than what the target system can handle.
### Examples
- Nginx
- F5
- HAProxy
- Citrix
- Azure Traffic Manager
- AWS

**NOTE:** You can use the machine to solve the questions from the hands-on section above.  
  
#### Q1: What is the User-Agent in the HTTP request in the given AWS load balancer log?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\aws-loadbalancer.log.zip  
  
**Answer Format:** XXXX/X.XX.X
```
curl/7.46.0
```

## Proxy Server
- A proxy server is hardware or software that acts as a gateway between client and server.
### Types of Proxy Servers
1. Forward - Most widely used. Directs requests from private network to Internet.
2. Transparent - Directs requests and responses to target without making changes.
3. Anonymous - Enables anonymous browsing.
4. High Anonymity - Makes it difficult to track client by excluding proxy server type and client IP in the request.
5. Distorting - Hides identity by defining itself as a proxy server of a website.
6. Data Center - Uses service over data centers (not connected to ISP). Quick response.
7. Residential - Passes all requests made by client. Unwanted and suspicious ads can be blocked.
8. Public - Free proxy server available for everyone. Accessible but slow.
9. Shared - Can be used by more than one person at same time. Preferred for fast connections and cost-free use.
10. SSL - Communication between client and server is encrypted.
11. Rotating - Separate IP address assigned to each client.
12. Reverse - Client does not communicate directly with server. Popular examples include "Varnish" and "Squid".
13. Split - Runs as two programs installed on two different computers.
14. Non-Transparent - Sends all requests to firewall. Clients are aware requests are sent to firewall.
15. Hostile - Eavesdrop on traffic between client and server.
16. Intercepting - Uses proxy and gateway features together.
17. Forced - Blocking and allowing policies.
18. Caching - Returns response according to caching mechanism.
19. Web - Web traffic.
20. Socks - Prevents external network components from obtaining info about client.
21. HTTP - Caching mechanism for HTTP protocol.
### Benefits of Proxy Server
- Private browsing
- Increased user security
- Allows client's IP to be hidden
- Allows to manage network traffic
- Saves bandwidth (with caching)
- Provides access to places with access restrictions
### How Does a Proxy Server
- Acts as a intermediary between client and server.
- Proxy server logs records of transactions (communication between client and server).
### The Importance of Proxy Servers for Security
- Client's IP is hidden (because server makes request on behalf of client).
### Examples
- Smartproxy
- Bright Data
- SOAX
- Oxylabs

**NOTE:** You can use the machine to solve the questions from the hands-on section above.

#### Q1: According to the given Squid Web Proxy Server log, to which port of the "letsdefend.io" address was the request sent?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\squid-proxy.log.zip
```
443
```

#### Q2: According to the given Squid Web Proxy Server log, how many different web addresses are there to send HTTP GET method requests?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\squid-proxy.log.zip
```
5
```
- http://virustotal.com
- http://amazon.com
- http://bleepingcomputer.com
- http://darkreading.com
- http://thehackernews.com

## Email Security Solutions
- Ensures security control of files in emails.
- Ensures security checking of URLs in emails.
- Detection and blocking of spoofed emails.
- Blocks emails with malicious content.
- Transmit info about harmful email as a warning.
### Examples
- FireEye NX
- IronPort
- TrendMicro Email Security
- Proofpoint
- Symantec

**NOTE:** You can use the machine to solve the questions from the hands-on section above.
#### Q1: According to the email security solution log, what is the email address of the recipient of the email?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\email.log.zip  
  
**Answer Format:** user@domain.io
```
jonas@letsdefend.io
```
Check the `toAddresses` key value.

#### Q2: What is the type of threat according to the email security solution log provided?  
  
**File Location:** C:\Users\LetsDefend\Desktop\QuestionFiles\email.log.zip
```
malware
```
Specified by the `classification` key value.
