# OWASP
- **Open Worldwide Application Security (OWASP)**: Non-profit foundation for improving software security.
## 2021 OWASP List
1. Broken Access Control
2. Cryptographic Failures
3. Injection
4. Insecure Design
5. Security Misconfiguration
6. Vulnerable and Outdated Components
7. Identification and Authentication Failures
8. Software and Data Integrity Failures
9. Security Logging and Monitoring Failures
10. Server-Side Request Forgery (SSRF)

<br>

The answers to the questions below can be found by searching online about OWASP.

#### Q1: What is the name of the tool that OWASP has prepared to help scan web applications for vulnerabilities?
<pre>ZAP</pre>
<br>

#### Q2: Which area does OWASP focus on?
A) Web Applications <br>
B) Server Management <br>
C) Wireless Security <br>
<pre>A</pre>
<br>

#### Q3: What is the name of the vulnerable web application project that OWASP wrote using Node.js for security researchers to improve themselves?
Answer Format: xxx_xxx
<pre>Juice_Shop</pre>
Juice Shop is an intentionally vulnerable web app ideal for security training, CTFs, and testing security tools.

<br>

#### Q4: What does the OWASP Top 10 list, published every few years, reveal?
A) Most critical security risks to mobile applications <br>
B) Most critical security risks to web applications <br>
C) Most encountered web application vulnerabilities <br>
D) Most encountered mobile application vulnerabilities <br>
<pre>B</pre>
<br>

# How Web Applications Work
- Web applications communicate with each other using HTTP.
- HTTP is layer 7, whereas TCP, IP, and Ethernet are used before HTTP.
- HTTP request is used to retrieve specific resource from web server.
<img src="https://ld-images-2.s3.us-east-2.amazonaws.com/Detecting+Web+Attacks/images/HTTP-Request.png"/>
- HTTP response message is a message sent from the server to client requesting the specific resource.
<img src="https://ld-images-2.s3.us-east-2.amazonaws.com/Detecting+Web+Attacks/images/HTTP-Response.png"/>

#### Q1: Which HTTP Request header contains browser and operating system information?
<pre>User-Agent</pre>
<br>

#### Q2: What is the HTTP Response status code that indicates the request was successful?
<pre>200</pre>
<br>

#### Q3: Which HTTP Request Method ensures that the submitted parameters do not appear in the Request URL?
<pre>POST</pre>
HTTP GET shows the parameters in the URL, whereas POST does not.

<br>

#### Q4: Which HTTP Request header contains session tokens?
<pre>Cookie</pre>
Sessions refer to cookies.

<br>

# Detecting SQL Injection Attacks
- SQL injections (SQLi) are critical attack vectors that involve the user inputting SQL queries.
## Types of SQL Injections
1. **In-band SQLi (Classic SQLi)**: SQL query sent and responded on same channel.
2. **Inferential SQLi (Blind SQLi)**: SQL queries that cannot be seen. Also called "Blind SQLi".
3. **Out-of-band SQLi**: SQL query is communicated through a different channel (i.e., Attacker receives replies for SQL queries via DNS).
- Attack examples:
  - Authentication bypass.
  - Command execution.
  - Exfiltration of sensitive data.
  - Creating/deleting/updating database entries.
## How to Prevent SQL Queries
- **Use framework**.
- **Keep framework updated**.
- **Always sanitize data received from user**.
- **Avoid use of raw SQL queries**.
## Detecting SQL Injection Attacks
- **Check all areas of a web request**.
- **Look for SQL keywords**.
- **Check any special characters**.
- **Familiarize yourself with common SQL injection payloads**.
- It is unwise to upload critical info such as access logs to a 3rd party tool (i.e., URL decoder), so keep this in mind.
- Can check if SQL injection attack is successful if you check the response (if there is one).
- The questions below will be based off of the provided .rar file.

<br>

#### Q1: What date did the exploitation phase of SQL Injection Attack start? 
<pre>01/Mar/2022:08:35:14</pre>
The attack initiated a few entries before the SQL statements were executed (GET request for Submit). If you compare the response size (beside the status code of web request), there is one entry that is particularly lower than the rest meaning the attack was quickly executed successfully.

<br>

#### Q2: What is the IP address of the attacker who performed the SQL Injection attack?
<pre>192.168.31.167</pre>
192.168.31.200 is the web server.

<br>

#### Q3: Was the SQL Injection attack successful? (Answer Format: Y/N)
<pre>Y</pre>
<br>

#### Q4: What is the type of SQL Injection attack? (Classic, Blind, Out-of-band)
<pre>Classic</pre>
Classic because the SQL injection attack is within same communication channel and visible.

<br>

# Detecting Cross Site Scripting (XSS) Attacks
- Allows malicious code to be executed on web applications.
## Types of XSS
1. **Reflected (Non-Persistent)**: XSS payload must be present in request. Most common.
2. **Stored XSS (Persistent)**: Attacker can permanently upload XSS payload to web application. Most dangerous.
3. **DOM Based XSS**: Payload executed as a result of modifying DOM environment so that client-side code behaves unexpectedly.
- Attackers can steal user session info.
- Capture credentials.
## Preventing a XSS Vulnerability
- **Sanitize user input data** - i.e., use HTML encoding.
- **Use a framework**.
- **Use the framework correctly**.
- **Keep framework updated**.
## Detecting XSS Attacks
- **Look for keywords**.
- **Learn about common XSS payloads**.
- **Check use of special characters**.
- Again the next set of questions are based on the attache .rar file.

<br>

#### Q1: What is the start date of the XSS attack? 
<pre>01/Mar/2022:08:53:20</pre>
<br>
Search in the file for the keyword "script" and look for the first entry that contains this keyword. That entry is the start of the attack.

#### Q2: What is the IP address of the attacker who performed the XSS attack?
<pre>192.168.31.183</pre>
<br>
192.168.31.200 is the web server.

#### Q3: Was the XSS attack successful? 
<pre>Y</pre>
Yes as the request was successful.

<br>

#### Q4: What is the type of XSS attack? (Reflected, Stored, Dom based)
<pre>Reflected</pre>
The payload is present in the file so the attack type is Reflected.

<br>

# Detecting Command Injection Attacks
- Command injection attacks occur when user input data is not sanitized and passed directly to OS shell.
- Web app and other server components are at risk.
## Preventing Command Injection
- **Always sanitize data.**
- **Limit user privileges.**
- **Use virtualization technology** (i.e., Docker).
## Detecting Command Injection Attacks
- **Examine all areas of a web request**
- **Look for keywords related to terminal language** (i.e., dir, ls, cp, cat, type).
- **Learn about commonly used command injection payloads**.
- **Shellshock** is a security vulnerabilitiy disclosed in 2014.
  - Bash execute environment variables unintentionally.
- Again the questions below are based off of the provided .rar file.

<br>

#### Q1: What is the date the command injection attack was initiated? 
<pre>01/Mar/2022:09:03:33</pre>
First check for terminal keywords. If you search for ls, two results appear in the text document. The first instance of ls occurring indicates when the attack was initiated.

<br>

#### Q2: What is the IP address of the attacker who performed the Command Injection attack?
<pre>192.168.31.156</pre>
192.168.31.200 is the web server address.

<br>

#### Q3: Was the Command Injection attack successful? 
<pre>N</pre>
No as there doesn't appear to be an output. The attacker also tried using && instead of ; to chain commands but doesn't give the desired output.

<br>

# Detecting Insecure Direct Object Reference (IDOR) Attacks
- Also known as broken access control.
- Allows one person to access object that belongs to another.
- Difficult to identify this attack because HTTP responses are not logged.
## Detecting IDOR Attacks
- **Check all parameters**.
- **Look at number of requests made to same page**.
- **Identify a pattern**.
- Same as before, the following questions will be based on the provided .rar file.

<br>

#### Q1: What is the IP address of the attacker who carried out the IDOR attack?
<pre>192.168.31.174</pre>
If you notice at the end of the file there are HTTP requests in quick succession belonging to 192.168.31.174 (presumably the attacker).

<br>

#### Q2: What is the date when the attack started?
<pre>01/Mar/2022:11:42:32</pre>
<br>
Started the entry where the attacker changed the id parameter (starting with id = 1).

#### Q3: Was the attack successful?
<pre>Y</pre>
The status code of 200 may indicate the attack was successful.

<br>

#### Q4: Was the attack carried out by an automated tool?
<pre>N</pre>
There are arbitrary time gaps in between HTTP requests, so no automated tool was used.

<br>

# Detecting RFI & LFI Attacks
- **Local File Inclusion (LFI)**: Attached file is not sanitized. This is located on the same web server the web app is being hosted on.
- **Remote File Inclusion (RFI)**: Similar to LFI, but file is hosted on another server.
- Always sanitize data received from user.
## Detecting LFI & RFI Attacks
- **Examine all web request fields**.
- **Look for special characters** (i.e., '/')
- **Be familiar with files used in LFI attacks**.
- **Look for acronyms such as HTTP and HTTPS**.
- The questions below refer to the attached .rar file

<br>

#### Q1: What is the attacker's IP address?
<pre>192.168.31.174</pre>
If you search for './' you can see the entries with the attacker's IP.

<br>

#### Q2: What is the start date of the attack?
<pre>01/Mar/2022:11:58:35</pre>
After searching for './' look at the first result.

<br>

#### Q3: Was the attack successful?
<pre>N</pre>
The web requests were successful but the response times are significantly lower compared to previous web requests. There doesn't appear to be any output either, so the attack wasn't successful.
