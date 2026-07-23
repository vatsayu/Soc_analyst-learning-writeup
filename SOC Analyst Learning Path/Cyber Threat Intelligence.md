- Cyber Threat Intelligence (CTI) aims to produce actionable output after processing and interpreting data.
	- Understanding TTPs of attackers.
- CTI also informs organizations about these outputs to minimize damages.

## CTI Lifecycle
### Planning and Direction
- Scope of intelligence.
- Figure out "what you want"
- Find answers to questions about intelligence obtained.
	- i.e., Does your organization have a SOC team?
### Information Gathering
- Determine what sources to collect data from.
- Internal or external.
- Examples:
	- Hacker forums
	- Ransomware blogs
	- Deep dark web forums and bot markets
	- Honeypots
	- Github/Gitlab/Bitbucket, etc.
### Processing
- Data is processed.
- Acts as a filter - clean data from false positives.
- Result is information we need.
## Analysis and Production
- Information is interpreted and analyzed.
- Reports are prepared.
## Dissemination and Feedback
- Necessary feedback should be given to make intelligence better and more efficient.

#### Q1: At what stage is big data created in cyber threat intelligence?
```
Information Gathering
```

#### Q2: Which of the following is not among the questions that the organization should ask itself during the Planning and Direction phase?  
  
- A- Does the organization have a SOC team?
- B- Has the organization been attacked before?
- C- Do the attacks target the organization or the individuals?
- D- Which EDR product is used in the organization?
```
D
```

#### Q3: Tom, the cyber security analyst in the SOC team, wants to collect data from the major intelligence sources for his organization. Tom wants to use decoy systems to detect potential attackers. Which intelligence source is Tom trying to bring in?
```
Honeypot
```
A honeypot describes what Tom wants to bring in.

## Types of Threat Intelligence
- Intelligence that L1 SOC and manager will receive will differ.
### Technical CTI
- Rulesets to protect organization against attacks.
- Typically used by SOC Analyst, Incident Responder.
### Tactical CTI
- Understand TTP of attackers.
- What vulnerabilities does attacker use, where do they operate, what are their motivations, what are their methods?
- Provided for SOC manager (leading technical teams).
### Operational CTI
- Similar to Tactical CTI - difference is Operational CTI focuses more on threat hunting.
- Focus on specific type of attack, or attacker.
- Used by Security Managers or threat hunting personnel.
### Strategic CTI
- For top execs of organization.
- Used for budgeting and planning for organization in long run.

#### Q1: What type of intelligence is appropriate for a threat hunter in the organization?
```
Operational Cyber Threat Intelligence
```

#### Q2: What type of threat intelligence is appropriate for an employee working as an L1 analyst in the organization?
```
Technical Cyber Threat Intelligence
```

## Determining the Attack Surface
- External Attack Surface - Creates attack surface to produce intelligence specific to organization.
- Gives organization visibility i.e., forgotton endpoints or subdomains.
- Find domains related to the main domain.
	- Use host.io service, viewdns.info, whoxy.com, dnslytics.com.
	- Can check which domains belong to organization and which one's don't by checking whois outputs of domains, or looking at their content.
- Find subdomains
	- SecurityTrails
	- AquaTone
	- Sublist3r
	- Assetfinder
- Find websites
	- httpx - Lists all domains responding to http/https requests.
	- httprobe
- Find login pages
	- Can be done with simple scripts (w/ Python)
- Technology used on websites
	- Wappalyzer - Detects technologies used on websites (i.e., Wordpress, MySQL)
	- Whatruns
	- Builtwith
	- Whatcms
- IP addresses
	- Make list of IP addresses using the domains and subdomains found.
	- Shodan
	- Binaryedge
	- Zoomeye
- Employee Mails
	- Should be monitored as emails can become compromised.
	- Recommend using a fake LinkedIn account.
	- SalesQL
	- RocketReach
	- Apollo
	- ContactOut
- Network Applications and Operating Systems
	- Allows us to track vulnerabilities actively or passively.
	- Shodan
- Bin numbers and Swift Codes
	- Important assets to be monitored like stolen credit cards.
	- Use public databases for bin numbers and swift codes.
	- bincheck.io
	- freebinchecker.com
	- bintable.com
	- wise.com
	- bank.codes
	- theswiftcodes.com
- SSL certificates
	- Determine if there is one for secure communication.
	- Censys
	- crt.sh

#### Q1: How many subdomains does "blueteam.training" have?
```
0
```
Couldn't install Sublist3r on my system, so I opted to search for an online subdomain finder tool and stumbled upon subdomainfinder.c99.nl.

#### Q2: What is the service of the page builder on letsdefend.io/blog/ ?
```
Webflow
```
I installed the Wappalyzer browser extension and used it on letsdefend.io/blog to discover the service used.

#### Q3: Which of the following is not one of the subdomain discovery tools?  
  
- Aquatone  
- Httpx  
- Sublist3r  
- SecurityTrails
```
Httpx
```
Httpx is used to send requests to websites.

#### Q4: Shodan can be used to detect IP blocks. (True or False)
```
True
```

## Gathering Threat Intelligence
- Useful collect threat data from many sources as possible to reduce false positives.
### Shodan
- Web-based server search engine.
- Can detect systems of specific country or organization.
- Alternatives are BinaryEdge, Zoomeye, Censys.
### Resources Providing IOCs
- Ips, domains, hashes, C2s.
- Allows to protect systems before they are infected.
- Take early actions.
- Resources:
	- Alienvault
	- Malwarebazaar
	- Abuse.ch
	- Malshare
	- Anyrun
	- Virustotal
	- Hybrid-Analysis
	- Totalhash
	- Phishunt
	- Spamhaus
	- Tor Exit Nodes
	- Urlscan
	- Zone-h
	- Rats
	- Sorbs
	- Barracuda
### Hacker Forums
- Hackers usually in these forums when in preparation for an attack.
- Can answer questions like directio nof attack, targets, methods used, and who is responsible.
### Ransomware Blogs
- Can view active ransomware groups in this link below:
	- http://ransomwr3tsydeii4q43vazm7wofla5ujdajquitomtd47cxjtfgwyyd.onion/
	- Must be viewed using Tor Browser - .onion extensions are not accessible by regular browsers.
### Black Markets
- Credit cards, RDP accesses, and prepaid accounts typically sold.
### Chatters
- Threat actors may share sensitive data in communications between each other.
- Frequently use applications such as Telegram, ICQ, IRC, and Discord.
### Code Repositories
- May contain full of sensitive data - database access information, login information, configuration files, secret API keys, etc.
- Github, Gitlab, Bitbucket.
### File Share Websites
- File share websites allow for sharing of files anonymously.
- Popular sites are Anonfiles, Mediafire, Uploadfiles, and File.io.
- Cannot download from these sites directly.
	- Two methods:
		- Guessing file name on sites.
			- Costly because requires lots of processing power.
		- Dork - Captures indexes of uploaded files.
			- Low cost - more effective and quick.
### Public Buckets
- Cloud-based environments that organizations or individuals use to store data.
- Examples: Amazon S3 Buckets, Azure Blobs, Google Cloud Storage.
### Honeypots
- One of the most effective ways to catch attackers.
- Systems easy to breach attractive to attackers.
- Intended for attackers to attack to collect IOCs.
- Examples: Kippo, Cowrite, Glastopf, Nodepot, Google Hack Honeypot, ElasticHoney, and Honeymail.
### SIEM/IDS/IPS/Firewalls
- Logs of such security products is useful to investigate.
- Gives good info about attackers.

#### Q1: What is the name of the data that identifies a threat, threat actor, malicious files, and plays an important role in threat intelligence?
```
IOC
```

#### Q2: What is the filter that allows us to search the name of an organization on Shodan?
```
org
```

#### Q3: Which of the following is not among the messaging applications that threat actors frequently use?  
  
- Telegram  
- ICQ  
- IRC  
- Instagram DM
```
Instagram DM
```

#### Q4: Practice question – Tom is a SOC analyst at “LetsDefend” organization. Tom received a notification stating that malware containing the name of his organization was uploaded to AnyRun. Find the IP address the malware is connecting to?  
  
File MD5 Hash: f6517b0a49bb245e1983d77d2f5b2f98
```
192.168.50.104
```
Can be found by searching up file hash on VirusTotal and navigating to the "Behavior" section.

#### Q5: How many processes does the malware with the MD5 Hash value "f6517b0a49bb245e1983d77d2f5b2f98" create?
```
2
```
Again if we look at VirusTotal under the behaviors section, the file creates two processes: `cmd.exe` and `rundll32.exe`.

## Threat Intelligence Data Interpretation
- Need to apply data (IP address, hashes, domains) to a filter and clean data -> gain intelligence.
- Classify and label data structure -> naviagte data and interpret faster.
#### Q1: What is the first data collected in threat intelligence called?
```
big data
```

## Using Threat Intelligence
- Interpreted data = consumable threat intelligence.
- Three areas:
	- External Attack Surface Management (EASM)
	- Digital Risk Protection (DRP)
	- Cyber Threat Intelligence (CTI)
	- All combined form XTI (Extended Threat Intelligence).
### External Attack Surface Management (EASM)
- Keep track of assets.
	- I.e., When domain purchased or discontinued.
- Alerts on new assets, DNS, internal IP, critical ports, SMTP, etc.
### Digital Risk Protection
- Focuses on mapped data (sources -> attack surface).
- Alarms:
	- Potential phishing domain detected
		- Should investigate domain that mimics or is structured similarly to our domains.
	- Rogue mobile application detected
		- I.e., Pirated APKs.
	- IP Address Reputation
		- Blacklist
		- Found in list of harmful IOCs
		- IP is involved with torrent activity
	- Impersonation of social media account

#### Q1: What part of extended threat intelligence contains vulnerability management?
```
EASM
```

#### Q2: If we receive an alarm from the threat intelligence product we use indicating that an IP address of our organization has been blacklisted. Which of the following actions would be incorrect to apply in this situation?  
  
A- The reason why the IP address is blacklisted should be determined.  
B- The reputation should be corrected by contacting the vendor whose IP address is blacklisted.  
C- The IP address should be disabled.  
D- A search should be made for the server to which the IP address points.
```
C
```
We shouldn't automatically assume that the IP address should be disabled; we need to investigate why it got blacklisted.

#### Q3: Mike is a SOC analyst at LetsDefend. The organization received intelligence indicating that the "fac941eefc8571e51aef69289b5903c4" MD5 value of one of its systems was found in malicious data. Mike needs to isolate the device from the network. Can you help us, what is the hostname of this endpoint?  
  
The user should go to the Endpoint Security page through the “Go There” option under the question, create a search, and find the hostname of the endpoint.
```
TempHost
```

## Threat Intelligence and SOC Integration
- Combining security products such as SIEM, SOAR, EDR, and firewalls provides us with highest visibility possible.
#### Q1: Which network security tool should be integrated to the threat intelligence products in order to prevent malicious inbound traffic coming into our organization in the fastest way?
```
firewall
```

#### Q2: Which of the following cannot be integrated with threat intelligence?  
  
- EDR  
- SIEM  
- SOAR  
- Nmap
```
Nmap
```

- If there is another domain mimicking the organization's website, the domain should be taken down.
