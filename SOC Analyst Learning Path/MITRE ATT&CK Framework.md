# Introduction to MITRE
- Founded in 1958 in the US as an organization.
- Purpose is to advance national security and serve public interest.
- MITRE ATT&CK - Adversarial Tactics, Techniques, and Common Knowledge.
  - Framework of a knowledge database created in 2013.
  - Cyber attacks are divided into stages and analyzed in depth.

<br>

#### Q1: In what year was the MITRE founded?
<pre>1958</pre>
<br>

#### Q2: In what year was MITRE ATT&CK Framework started to be developed?
<pre>2013</pre>
<br>

# Matrix
- A matrix is a visualization method to clasify attack methods of attackers.
- Three types for MITRE ATT&CK framework:
  - **Enterprise Matrix**: Contains more digital systems and is more common.
    - Sub-matrices: PRE, Windows, macOS, Linux, Cloud, Network, Containers 
  - **Mobile Matrix**: Contains info about cyber security of mobile devices.
    - Sub-matrices: Android, iOS.
  - ICS (Industrial Control Systems) Matrix: Contains info collected for cyber security of industrial control systems.

<br>

#### Q1: What is the name of the images on the tactic and techniques in the MITRE ATT&CK Framework?
<pre>Matrix</pre>
<br>

#### Q2: What is the matrix of information about the cybersecurity of Windows, Linux, macOS, Azure AD and Office 365 platforms?
<pre>Enterprise</pre>
<br>

#### Q3: What is the matrix that contains the information about the cyber security of Android and iOS platforms?
<pre>Mobile</pre>
<br>

# Tactics
- Tactic represents purpose of cyber attacker and their rationale.
  - i.e., Reconnaissance, Resource Development, Initial Access, Execution.
-  14 tactics for Enterprise and Mobile matrix.
-  12 tactics for ICS matrix.

<br>

#### Q1: What is the ID of the "Lateral Movement" tactic in the Enterprise matrix?
<pre>TA0008</pre>
Go to MITRE ATT&CK website. Search for Lateral Movement (Enterprise) to find the ID.

<br>

#### Q2: When was the "Persistence" tactic in the mobile matrix created? 
<pre>17 October 2018</pre>
Go to MITRE ATT&CK website. Search for Persistence (Mobile) to find when the tactic was created.

<br>

#### Q3: What is the name of the tactic in Enterprise, Mobile and ICS matrices which is under the techniques related to obtaining higher-level permission on the target system/network?
<pre>Privilege Escalation</pre>
Privilege Escalation describes this tactic.

<br>

# Techniques and Sub-Techniques
- Tactics only show attacker's goals; not detailed info about their attack method.
- Techniques and sub-techniques shows attackers methods to achieve their goals.
- Like with matrices, techniques are divided into Enterprise, Mobile, and ICS.
  - Enterprise has the most techniques (193, 401).
  - ICS has no sub-techniques.
- Procedure shows usage examples of techniques/sub-techniques.

<br>

#### Q1: What is the name of the technique with the ID T1055 among the Enterprise techniques?
<pre>Process Injection</pre>
Go to MITRE ATT&CK website. Search for T1055 and select the result related to Enterprise.

<br>

#### Q2: Among the Enterprise techniques, which platform is the technique with the ID T1112 for?
<pre>Windows</pre>
Go to MITRE ATT&CK website. Search for T1112 and read the description of the technique.

<br>

#### Q3: Under which tactic is the "Supply Chain Compromise" technique which is among the Enterprise techniques?
<pre>Initial Access</pre>
Go to MITRE ATT&CK website. Search for Supply Chain Compromise and select the first result (not sub-technique). If you read, the tactic associated with this technique is Supply Chain Compromise.

<br>

# Mitigations
- Mitigations are actions taken to respond to techniques in MITRE ATT&CK matrix.
- Like with matrices and tactics, they can be grouped into Enterprise, Mobile, and ICS.

<br>

#### Q1: What is the name of the mitigation with the ID M1032 among the Enterprise mitigations?
<pre>Multi-factor authentication</pre>
Go to MITRE ATT&CK website and search for M1032.

<br>

#### Q2: What is the name of enterprise mitigation that recommends “digital signature verification should be implemented to prevent the untrusted codes from working on enterprise devices”?
<pre>Code signing</pre>
Go to MITRE ATT&CK website and search for digital signature. Code signing matches this description.

<br>

# Groups
- APT (Advanced Persistent Threat) groups are hacker groups that carry out cyber attacks in a targeted and systematic way.
- May be government supported.
- Maps attack groups to systems and techniques.

<br>

#### Q1: What is the name of the software that is associated only with the "System Information Discovery" technique among the software utilized by the OilRig APT group?
<pre>Systeminfo</pre>
On MITRE ATT&CK website, search for OilRig APT group. Under the software section, search for the software that only lists 1 technique - System Information Discovery.

<br>

#### Q2: What is the name of the APT group whose “Associated Groups” information includes the names “GOLD NIAGARA”, “ITG14” and “Carbon Spider”?
<pre>FIN7</pre>
If you search for "GOLD NIAGARA" and select "Groups" result, you can find the group associated.

<br>

# Software

<br>

#### Q1: For which platform is the software named “Cryptoistic” utilized by “Lazarus Group” APT group meant for?
<pre>macOS</pre>
Search for Cryptoistic then you can see the platform on the right side of the page.

<br>

#### Q2: What is the type of software named “Rotexy” for Android platforms?
<pre>Rotexy</pre>
Search for Rotexy then you can see the type on the right side of the page.

<br>

#### Q3: What is the name of the APT group that utilizes the software named “PUNCHBUGGY” targeting POS networks?
<pre>FIN8</pre>
Search for "PUNCHBUGGY". The APT group is specified in the description.
