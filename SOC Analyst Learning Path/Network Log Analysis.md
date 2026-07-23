## Generic Log Analysis (Netflow)
- Netflow is a network protocol that collects IP traffic info.
	- Developed by Cisco.
### Key Benefits of Netflow
- Billing and Accounting
- Network Design and Optimization
- Network Monitoring i.e., frequently used ports and traffic patterns
- Quality of Service (QoS) Measurement: Monitors service quality and performance.
- Security Analysis
### How NetFlow Works
- Stateful - monitors and reports all IP traffic in/out of an interface.
- Flow - Packets with shared attributes.
	- Attributes:
		- Source and Destination IP
		- Source and Destination Ports (TCP/UDP)
		- IP Protocol
		- Interface Info
		- IP Version (IPv4/IPv6)
- Exports data in binary format.
	- Can use collector/analyzer tool to convert to readable format.

#### Q1: Can “Layer 7 - Application Layer” information be obtained with Netflow analysis?  
  
Answer Format: Y/N
```
N
```
Netflow is only capable of layer 3.

#### Q2: Which of the followings are not produced through Netflow logs?  
  
- IP Information  
- XFF IP Information  
- Port Information  
- Interface Information
```
XFF IP Information
```
XFF (X-Forwarded-For) is a HTTP Request header used to identify originating IP address of a client connecting to a web server through a proxy. Netflow does not produce this information.

#### Q3: What types of attacks can be detected with Netflow data?  
  
- Network Anomaly Detection  
- Detection of an Infected System  
- Detection of malicious applications running on the Endpoint  
- Suspicious Domain Requests
```
Network Anomaly Detection
```
Detection of infected system or malicious applications typically occur on an endpoint - something Netflow does not detect. Suspicious domain requests is layer 7 - again something Netflow is not capable of.

#### Q4: According to the NetFlow data above, what could it be to see 10k requests from different source IPs to the same destination within 2 minutes?  
  
- SYN Flood  
- UDP Flood  
- ICMP Flood  
- DNS Flood
```
UDP Flood
```
In the screenshot you can see the protocol being used is UDP.

#### Q5: Which of the following is not true according to the NetFlow data above?  
  
A) Total number of package is 1.  
B) The amount of data transmitted is 71 bytes.  
C) NTP service is definitely running on the target port 123.
```
C
```
NTP doesn't necessarily always run on port 123. Attackers can configure services such as NTP to use other port numbers.

## Firewall Log Analysis
- Some key log fields you might see in firewall logs:
	- devname = Hostname
	- devid = Device ID
	- subtype = Sub log type (i.e., vpn, webfilter, virus, ips)
	- transip = NAT IP info
	- transport = NAT port info
1. Check IP and port info
2. Examine whether traffic reached target (check action field)
- Action field values:
	- client-rst: Communication terminated by client.
	- server-rst: Communication terminated by server.

#### Q1: **Note:** Use the "/root/Desktop/QuestionFiles/firewall.log" file for solving the questions below.  
  
**Question:** How many different ports did the attacker attempt to access?
```
12
```
443, 80, 22, 3389, 1521, 445, 139, 3306, 1453, 23, 21, 53

#### Q2: What kind of attack/activity could have been made according to the logs above?  
  
A) Brute-Force Attack  
B) Port-scan activity  
C) TCP-SYN-Flood Attack  
D) No suspicious activities detected
```
B
```
The logs show various destination ports were accessed.

#### Q3: How does Firewall determine whether to forward an incoming packet to the destination or not?  
  
A) By analyzing behaviorally  
B) According to the rule policy  
C) According to the size of the traffic  
D) According to the location information
```
B
```
A packet is allowed/blocked depending on rules configured in the firewall.

#### Q4: How many open ports did the attacker detect?
```
3
```
Ports 443, 53, and 1521 are open (indicated by allow action).

#### Q5: Will the attacker get a response from the Firewall stating that its access request was blocked?  
  
Answer Format: Y/N
```
Y
```
Yes. Attempting to access other ports shows that the request was blocked.

## VPN Log Analysis
- VPN allows for access of sites that you normally cannot access because of your location (i.e., accessing work network from home).
### VPN Deployment Methods
- Integrated into firewalls.
- Standalone dedicated VPN appliances.
- Logs may originate from firewall devices or VPN systems.
### Key Log Fields
- remip: IP address that established VPN connection.
- Most critical elements are:
	- Source IP initiating connection
	- Authenticated username
	- Access request result

**Note:** Check the VPN logs in the previous question above.

#### Q1: Which of the followings are true for the user3 VPN User?  
  
A) Brute-Force Attack  
B) user3 made a successful VPN connection  
C) There were failed login attempts from different locations within short period of time  
D) user3 made a successful VPN connection from the US location
```
C
```
In the logs the error is "Invalid username or password". We see multiple entries of this from different locations in a short span of time.

**Note:** Use the "/root/Desktop/QuestionFiles/vpn.log" file for solving the questions below.
#### Q2: Which of the following is not a type of VPN?  
  
A) SSL-VPN  
B) Site-to-Site VPN  
C) IPSec VPN  
D) DNS over VPN
```
D
```

#### Q3: VPN only works on firewall devices. (True/False)
```
False
```
VPNs can also operate on dedicated systems.

#### Q4: Which one is true for the "letsdefend" user logs?  
  
A) Brute-Force Attack  
B) 4 Successful VPN connections were established with Letsdefend user  
C) Letsdefend user has successfully logged in from DE location
```
A
```

## Proxy Log Analysis
- **Transparent Proxy**: The target server can see the real source IP.
- **Anonymous Proxy**: The target server cannot see the real source IP.
- Examples: Cisco Umbrella, Forcepoint Web Security Gateway, Check Point URL Filtering, Fortinet Secure Web Gateway.

#### Q1: Proxy is only used for accessing the internet via the web. (True/False)
```
False
```
Not necessarily, can also occur within private networks (no Internet).

#### Q2: Mar 30 19:07:16 10.60.28.21 CEF:0|Forcepoint|Security|8.5.4|1900|Transaction permitted|164| act=permitted app=https dst=18.11.96.7 dhost=letsdefend.io dpt=443 src=172.20.40.42 spt=59228 suser=user1 requestMethod=CONNECT cs1Label=Policy cs1=default-user-policy request=https://letsdefend.io/  
  
According to the Proxy log above, which of the following is not true?  
  
A) SSL/TLS used.  
B) User1 made the query.  
C) The proxy device has blocked this request.  
D) The domain accessed works on the server with the address "18.11.96.7".
```
C
```
act=permitted

#### Q3: Through which logs do we verify the response from the requested target in the proxy log above? (assuming that there are Firewall, AV, DLP, IPS/IDS, EDR, WAF devices in the environment.)  
  
A) From the antivirus logs  
B) From Email Gateway logs  
C) From Firewall logs  
D) From DLP logs
```
C
```

#### Q4: Mar 30 19:07:16 10.60.28.21 CEF:0|Forcepoint|Security|8.5.4|1900|Transaction permitted|164| act=permitted app=https dst=18.11.96.7 dhost=letsdefend.io dpt=443 src=172.20.40.42 spt=59228 suser=user1 requestMethod=CONNECT cs1Label=Policy cs1=default-user-policy request=https://letsdefend.io/  
  
When the above proxy log record turns into an alert, which action below is not required?  
  
A) Checking domain reputation  
B) Dynamic analysis of the accessed address  
C) Controlling which different systems accessed the requested domain  
D) Obtaining information by contacting the user who made the request  
E) Blocking access to the domain  
F) Check of Windows Application Events of the requesting system
```
F
```
All except F are required to perform should the log record be an alert. Checking Window Application Events won't do much to assist in the investigation, so its not required.

## IDS/IPS Log Analysis
- Signature Database: Centralized repository of rules.
- Open source code signatures:
	- https://rules.emergingthreats.net/open/suricata-5.0/rules/
- Direction of attack (inbound/outbound) should be checked.
- Event severity level should be checked.
- Check if attack is running on target port.
- Check if action taken is just detection or if it blocking.

#### Q1: IDS is a system that …………. the attacks. IPS is a system that …………. the attacks.  
  
Fill in the blanks.  
  
A) prevent - detect  
B) detect - prevent  
C) detect - detect  
D) prevent - prevent
```
B
```

#### Q2: {"timestamp":"2022-06-13T08:25:36", "in_iface":"ens1f1", "event_type":"alert","vlan":1,"src_ip":"192.168.1.11", "src_port":53,"dest_ip":"172.16.2.25", "dest_port":1029,"proto":"UDP", "alert":{"action":"allowed", "gid":1, "signature_id":2811577, "rev":3, "signature":"ETPRO TROJAN Possible Virut DGA NXDOMAIN Responses", "category":"A Network Trojan was detected", "severity":1, "metadata":{"updated_at":["2021_09_22"],"created_at":["2015_06_18"]}}, "app_proto":"failed"}, "payload":"dnV5ZWltLmNvbQo=", "payload_printable":"vuyeim.com", "stream":0}  
  
Answer the following questions according to the above referenced IDS log:  
  
Which of the following is not correct?  
  
A) The system making malicious domain request may be infected.  
B) The relevant domain has not been accessed.  
C) The DNS server has responded to the domain request.  
D) The domain categorized as DGA is vuyeim.com.
```
B
```
The log indicates `action: allowed` meaning the domain was accessed.

#### Q3: {"timestamp":"2022-06-13T08:25:36", "in_iface":"ens1f1", "event_type":"alert","vlan":1,"src_ip":"192.168.1.11", "src_port":53,"dest_ip":"172.16.2.25", "dest_port":1029,"proto":"UDP", "alert":{"action":"allowed", "gid":1, "signature_id":2811577, "rev":3, "signature":"ETPRO TROJAN Possible Virut DGA NXDOMAIN Responses", "category":"A Network Trojan was detected", "severity":1, "metadata":{"updated_at":["2021_09_22"],"created_at":["2015_06_18"]}}, "app_proto":"failed"}, "payload":"dnV5ZWltLmNvbQo=", "payload_printable":"vuyeim.com", "stream":0}  
  
What is the IP address related to the malicious domain?
```
172.16.2.25
```
The IP address associated refers to the `dest_ip`

#### Q4: {"timestamp":"2022-06-13T08:25:36", "in_iface":"ens1f1", "event_type":"alert","vlan":1,"src_ip":"192.168.1.11", "src_port":53,"dest_ip":"172.16.2.25", "dest_port":1029,"proto":"UDP", "alert":{"action":"allowed", "gid":1, "signature_id":2811577, "rev":3, "signature":"ETPRO TROJAN Possible Virut DGA NXDOMAIN Responses", "category":"A Network Trojan was detected", "severity":1, "metadata":{"updated_at":["2021_09_22"],"created_at":["2015_06_18"]}}, "app_proto":"failed"}, "payload":"dnV5ZWltLmNvbQo=", "payload_printable":"vuyeim.com", "stream":0}  
  
Which of the following is a true statement?  
  
A) The request is blocked by the firewall.  
B) The related IDS has caught the DNS request in the return traffic.  
C) The category of the IDS rule is in the "DNS attack" category.

```
B
```
The request was allowed as indicated by `action: allowed`. The category pertaining to this log is `A Network Trojan was detected`.

#### Q5: Which of the following information is normally not included in the IDS/IPS alarm outputs?  
  
A) Payload information  
B) IP and Port information  
C) Parent process information  
D) Action information  
E) Signature information
```
C
```

## WAF Log Analysis
- SSL Offload: Decryption of SSL-encrypted traffic.
	- Helps WAFs examine content of HTTPS traffic.
- WAFs are first to detect web attacks.
- ASP: Active Server Pages
	- Created by Microsoft to make web pages do things dynamically.
- Useful for detecting the following:
	- Known web vulnerabilities
	- SQL injection, XSS attack, code injection, directory traversal
	- Suspicious method usage (i.e., PUT, DELETE)
	- Top requesting IP Information
	- Most requested URL

#### Q1: date=2022-01-26 time=19:47:26 type=attack main_type="Signature Detection" sub_type="SQL Injection" severity_level=High proto=tcp service=https/tls1.2 action=Alert policy="Alert_Policy" src=199.26.150.138 src_port=56334 dst=172.16.10.10 dst_port=443 http_method=get http_url="?v=" OR 1 = 1 -- -" http_host="app.letsdefend.io" http_agent="Mozilla/5.0 (Nikto/2.1.6)" srccountry="Italy" attack_type="SQL Injection"  
  
Which of the following is not true according to the WAF log above?  
  
A) The request has reached the server  
B) The server responded to the request successfully  
C) According to the log record, the request came through the automated web browsing tool  
D) The request method is GET

```
B
```
It doesn't necessarily mean the server responded to the request successfully. We only got a detection or an alert based on this log.

The automated web browsing tool that was used is Nikto.

#### Q2: Which of the following actions should be taken when the above WAF log is examined?  
  
A) Whether the attack was successful or not should be simulated.  
B) Requests with high source port numbers should be blocked on the firewall.  
C) SSL certificate should be reviewed.

```
A
```
Need to determine magnitude of the attack, which users or systems were affected.

## Web Log Analysis
- Common web servers are:
	- Microsoft IIS
	- Apache
	- Nginx
- Web servers do not write content of data sent to server by POST or PUT.

### Web attack types and sample request URLs
<img src="https://ld-images-2.s3.us-east-2.amazonaws.com/Network+Log+Analysis/images/WEB.png"/>

#### Q1: Which of the following is not an HTTP request method?  
  
A) GET  
B) OPTIONS  
C) TRACE  
D) HEAD  
E) BLOCK
```
E
```


**Note:** Use the "/root/Desktop/QuestionFiles/http.log" file for solving the questions below.  
#### Q2: Are there any SQL injection attacks with a status code of 200? (True or False)
```
True
```
`cat http.log | egrep -i 'select|union|insert|concat' |grep '200' |grep 'OK' |more`

#### Q3: Identify the highest requesting IP address.
```
192.168.203.63
```
`cat http.log | awk '{print $3}' |sort -n |uniq -c | sort -n`

#### Q4: How many web requests are made with "DELETE" method in total?
```
223
```
`cat http.log | awk -F '\t' '$8 == "DELETE"' | wc -l`
Did this with the help of ChatGPT. Make sure to provide the log format to tailor towards the `cat` command.

#### Q5: Are there web logs with “Nmap Scripting Engine” in the user-agent information among the web requests made? (True or False)
```
True
```
`cat http.log | grep 'Nmap Scripting Engine' > /dev/null && echo True || echo False`
Using the above command returned true - meaning there are web logs with Nmap Scripting Engine.

## DNS Log Analysis
- SOC analysts use DNS logs to check which domains were requested and when.
- On Windows servers they are located in:
	- Application and Services Logs -> Microsoft -> Windows -> DNS-Server\Audit

#### Q1: Which of the following is not a DNS record type?  
  
A) MX  
B) NS  
C) A  
D) IP
```
IP
```

#### Q2: DNS log;  
Feb 5 09:12:11 ns1 named[80090]: client 192.168.10.3#3261: query: dns.google IN A  
  
Firewall log;  
date=2022-05-21 time=09:12:13 type="traffic" subtype="forward" srcip=192.168.10.3 srcport=50495 srcintfrole="lan" dstip=8.8.4.4 dstport=853 dstintfrole="wan" proto=6 action="accept"  
  
What could the suspicious activity be at the DNS and firewall logs above?  
  
A) DNS Flood  
B) DNS Tunnel  
C) DNS over HTTPS  
D) DNS Hijacking
```
C
```
Port 853 is used for DNS over TLS (or HTTPS). There is only one query so no flooding. There is not strange or large data. Nothing suggests DNS responses were altered. So DNS over HTTPS has to be the answer.

#### Q3: Mar 5 19:12:11 ns1 named[80090]: client 172.16.11.34#3261: query: am4wuz3zifexz5u.onion IN A  
  
What could the suspicious activity be at the DNS log above?  
  
A) DNS Proxy  
B) DNS Tunnel  
C) DNS over HTTPS  
D) Access to the TOR network
```
D
```
The `.onion` indicates TOR, so D is the activity mentioned in the DNS log.

- Firewalls cannot create web logs.
- When a request is blocked by a WAF, this is not visible in the web server logs.
