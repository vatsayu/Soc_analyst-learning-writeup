# Introduction to Cyber Kill Chain
- Lockheed Martin is a security and aerospace corporation, established in 1995.
- Cyber kill chain was created in 2011 by Lockheed Martin to model attacks of attackers.
  - https://www.lockheedmartin.com/en-us/capabilities/cyber/cyber-kill-chain.html
- Helps SOC analyst better understand stages of cyber attack.
- Enables organization to determine where and how severe security flaws are.

<br>

#### Q1: Which organization was the Cyber Kill Chain model developed by?
<pre>Lockheed Martin</pre>
<br>

#### Q2: In what year was the organization that developed the Cyber Kill Chain model founded?
<pre>1995</pre>
<br>

#### Q3: In what year was the Cyber Kill Chain model developed?
<pre>2011</pre>
<br>

# Cyber Kill Chain Steps
1. Reconnaissance
2. Weaponization
3. Delivery
4. Exploitation
5. Installation
6. Command and Control (C2)
7. Actions on Objectives

<br>

#### Q1: How many steps does the Cyber Kill Chain model consist of?
<pre>7</pre>
<br>

# Reconnaissance
- Attacker obtains info about target system.
- **Passive reconnaissance**: Collect info about target without physical engagement.
  - i.e., Archived websites. 
- **Active reconnaissance**: Acquiring info about target with engagement.
  - i.e., Sending a request to a web server.

<br>

#### Q1: What is the step in the Cyber Kill Chain model where the information gathering takes place?
<pre>Reconnaissance</pre>
<br>

#### Q2: The Real-life attack Scenario items above explain an aspect of an actual cyber attack. Based solely on this information, what is the number of distinct actions taken during the "Reconnaissance" phase, which is the first step of the Cyber Kill Chain?
<pre>3</pre>
1. Security vulnerability with code CVE-2019-0604 has been found.
2. Security vulnerability was exploited.
3. "Powershell Empire" backdoor deployed on target system.

<br>

# Weaponization
- Uses info from previous stage to gather tools needed for the attack.
- i.e., Creating malware, exploits.
- Blue teams can take measure such as installing security updates, checking for vulnerabilities, analyzing impact of new cyber attack tools.

#### Q1: How many separate activities were performed in the "Weaponization" phase, the second step of the Cyber Kill Chain, according to the Attack Scenario items above? 
<pre>2</pre>
1. Phishing email template was generated.
2. Included in the phishing email is a Word document which contained malicious macro code.

<br>

# Delivery
- Attacker executes cyber attack.
- i.e., Malicious URL by email, malware via social media.
- Blue teams should scan email attachments, monitor server logs, perform detailed analysis of suspicious activities.

<br>

#### Q1: According to the Attack Scenario items above, how many different actions were performed in the "Delivery" phase, the third step of the Cyber Kill Chain?
<pre>2</pre>
1. Employee picks up USB (malicious) from sidewalk.
2. Malware was executed on a USB stick after employee plugs USB into their machine.

<br>

#### Q2: How many separate activities were performed in the "Weaponization" phase, the second step of the Cyber Kill Chain, according to the Attack Scenario items above?
<pre>2</pre>
1. Malware was embedded into "putty.exe" with the help of Metasploit tool.
2. Malware was transferred to several USB sticks.

<br>

# Exploitation
- Attacker ensures malicious content is activated at this stage.
- This step may fail if exploit or tool not suitable on target machine.
- Blue teams can train employees on security awareness, constantly monitor system security operations, and conduct pentests on a regular basis.

<br>

# Installation
- Attacker attempts to maintain persistence on target system.
- Privilege escalation involved.
- i.e., Install malware, backdoor, web shell, firewall rule, or scheduled task.
- Blue teams should assume attacker is present in the system.
  - Network security monitoring.
  - Restrict access to file systems.
  - Detect anomalies and find root cause.

## Q1: According to the above detection scenario, what is the Cyber Kill Chain step where the attacker fails and the attack is detected? 
<pre>4</pre>
The scenario describes weaponization. It is at this step that the attack could fail because the tool is not suitable on the machine.
<br>

# Command and Control (C2)
- Attacker established Command and Control (C2) server to deliver commands to system.
- Attackers performs any actions to necessitate communicate between C2 server and victim.
- Blue teams should detect for any C2 systems.

<br>

#### Q1: What is the last Cyber Kill Chain step in which the attacker is successful, according to the aforementioned detection scenario? 
<pre>6</pre>
Last step is 6. Command and Control (C2).

<br>

# Actions on Objectives
- Attacker takes planned actions at start of cyber attack.
- i.e., Delete critical info, encrypt files (ransomware), collect user credentials.
- It may still be possible for blue teams to detect malicious activity.

<br>

#### Q1: The usage of the "SDelete" tool for data deletion by the APT group "Cobalt Group" is an activity at which stage of the Cyber Kill Chain? 
<pre>7</pre>
The usage of the tool is associated with step 7. Actions on Objectives.
