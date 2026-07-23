# Detecting Web Attacks 2

## Detecting Open Redirection Attacks
- **Open redirection**: Redirects users to differnet URL w/o proper validation or sanitization.
- Attackers use this to trick users into visiting websites.
- Typically a legit URL is created with a malicious URL as a parameter.
- Recommended to validate, sanitize, and implement proper authentication and authorization for redirects.

<br>

### Redirection Types / Vectors
1. **URL-based open redirection**: Malicious website in URL parameter.
2. **JavaScript-based open redirection**: Malicious URL obtained using JS code or input data.
3. **Meta refresh-based open redirection**: Website uses "meta refresh" tag to redirect users to another URL.
4. **Header-based open redirection**: Website uses HTTP headers to perform a redirect.
5. **Parameter-based open redirection**: Website uses parameter for redirect (value not sanitized).

<img src="https://letsdefend-images.s3.us-east-2.amazonaws.com/Courses/Detecting-Web-Attacks-2/open+redirection/Bash+URL.png"/>

<br>

### Impact of Open Redirection
1. Phishing attacks.
2. Malware distribution.
3. Social engineering attacks.
4. Reputation damage.
5. Legal and regulatory consequences.

<br>

### Detecting Open Redirect Attacks
1. Consecutive query string parameters (i.e., http://website.com/param.php?next=).
2. Payloads can bypass techniques like:
   1. Localhost.
   2. CDIR.
   3. Decimal bypass (i.e., http://2130706433 = http://127.0.0.1)
   4. Hexadecimal bypass (i.e., http://0x7f000001 = http://127.0.0.1)
- Can use the following regec to detect open redirection attacks:
  - /^.*"GET.*\?.*=(https%3a%2f%2f[a-z0-9-]+%2e[a-z]{2,}).+?.*HTTP\/.*".*$/gm

<img src="https://letsdefend-images.s3.us-east-2.amazonaws.com/Courses/Detecting-Web-Attacks-2/open+redirection/decoded-open.png"/>

In the above image, attacker wants to redirect to google.com using ?pro parameter.

Answer the following questions using the provided access log.

<br>

#### Q1: What date did the exploitation phase of Open Redirection start? Format: dd/MMM/yyyy HH:mm:ss
<pre>27/Apr/2023 15:45:22</pre>
I searched for "local" then noticed a couple of suspicious entries. Some entries contained "http://victim.com/" so I kept scrolling up until I saw the first instance.

<br>


#### Q2: What is the IP address of the attacker who performed the Open Redirect attack?
<pre>86.236.188.85</pre>
This is based off of the same entry used to find the date of the start of exploitation phase.

<br>

#### Q3: What was the parameter that attacked?
<pre>postID</pre>
<br>

### Detecting Directory Traversal Attacks
- **Directory traversal**: Access files and directories outside of web server's root directory.
- Aka dot-dot-slash attack.
- Used to gain unauthorized access to sensitive data and execute arbitrary code.
- i.e., Attack can add `../` to a URL. http://example.com/profiles/picture.php?name=../../etc/passwd
- Similar to **Local File Inclusion (LFI)**
  - Difference is source of input.
  - Directory traversal manipulate input used to access files on web server.
  - LFI manipulate input used to include local files within web app.
 
<br>

### Directory Traversal Possible Vectors
1. User input (../)
2. Cookies
3. HTTP headers: Manipulating Referer or User-Agent header.
4. File upload
5. Direct requests: Guessing or brute-forcing file names or paths.
6. URL manipulation
7. Malicious links

<br>

### Impact of Directory Traversal
1. Disclosure of sensitive data.
2. Execution of arbirtrary code (malware or backdoors).
3. Denial of service.
4. System compromise

<br>

### Prevention Methods for Directory Traversal Attacks
- Input validation and sanitization.
- Access controls.
- Relative file paths.
- Whitelisting: only specific characters allowed in file name parameter.
- Secure coding practices: i.e., avoid using user input in path concatenation, eval() and system().
- Web application firewall (WAF).

<br>

### Detecting Directory Traversal Attacks
Example payloads:
<img src="https://letsdefend-images.s3.us-east-2.amazonaws.com/Courses/Detecting-Web-Attacks-2/directory+traversal/img5.png"/>

Popular files:

**Linux**
- /etc/issue
- /etc/passwd
- /etc/shadow
- /etc/group
- /etc/hosts

**Windows**
- c:/boot.ini
- c:/inetpub/logs/logfiles
- c:/inetpub/wwwroot/global.asa
- c:/inetpub/wwwroot/index.asp
- c:/inetpub/wwwroot/web.config
- c:/sysprep.inf

<br>

Answer the following questions below using the provided file.

<br>

#### Q1: What date did the exploitation phase of Directory Traversal start? Format: dd/MMM/yyyy HH:mm:ss
<pre>23/Apr/2023 00:16:57</pre>
I searched using the common payloads i.e., %2e. The first result indicates the date when the attack started.

<br>

#### Q2: What is the IP address of the attacker who performed the Directory Traversal attack?
<pre>123.114.236.235</pre>
This is based off the entry when the attack started.

<br>

#### Q3: What was the parameter that attacked?
<pre>uid</pre>
<br>

## Detecting Brute Force Attacks
- **Brute forcing**: Guessing password or auth token by trying every possible combination until correct one is found.
- Effective on web apps with poorly implemented access controls or configurations.
<img src="https://letsdefend-images.s3.us-east-2.amazonaws.com/Courses/Detecting-Web-Attacks-2/brute+force/img1.png"/>
- The above code is susceptible to brute force attacks because it allows unlimited login attempts.

### Impact of Brute Forcing
1. Denial of service
2. Data leakage
3. Account takeover
4. Password reuse
5. Reputational and legal consequences

### Prevention Methods for Brute Forcing
- Implement CAPTCHA
- Limit rate of login attempts
- Use multi-factor authentication
- Monitor login attempts
- Use strong passwords and password policies

### WAF Capabilities
- IP blocking
- User behavior analysis

### Detecting Brute Force Attacks
- Collect and store authentication logs.
- Look for patterns of suspicious activity.
- Analyze network traffic logs.
- Deploy IDS or IPS.
- Block malicious IPs.

### Detecting Brute Force Attacks in Nginx Logs
- Log analysis tools
- Regular expressions
   - i.e., /^(\S+) \S+ \S+ \[.*?\] "(POST|GET) \/login\.php.*?" (401|403) \d+ ".*?" ".*?"/gm 
- Fail2ban
- IP blocking

The questions below are based on the provided access log file.

#### Q1: What is the attacker's user agent?
<pre>Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.5615.50 Safari/537.36</pre>
The access log shows repeated requests indicating a brute force attack. Attacker's user agent can be obtained from these entries.

<br>

#### Q2: What is the IP address of the attacker who performed the Brute Forcing attack?
<pre>146.241.231.73.240</pre>
<br>

#### Q3: What date did the Brute Forcing successfully complete to login form? Format: dd/MMM/yyyy HH:mm:ss
<pre>26/Apr/2023 21:44:03</pre>
This can be found after a repeated set of requests coming from the attacker's IP.

<br>

## Detecting XML External Entity Attacks
- XXE (XML External Entity) affects applications that parse XML input.
- Attacker injects malicious XML data.
- XML parser processes external entities controlled by attacker.
- Examples of input points:
   1. Form fields that accept XML input
   2. XML files uploaded by users
   3. APIs that accpet XML requests
   4. XML files used for configuration or other purposes

### Impact of XML External Entity
1. Information disclosure.
2. Server-side request forgery (SSRF): Make requests on behalf of server - allows for scan internal networks and carry out further attacks.
3. Denial of Service (DoS)
4. Remote code execution (RCE)

### Prevention Methods for XML External Entity
- Disable external entities.
- Input validation and sanitization.
- Use secure parsers.
- Use whitelist filtering.
- Implement access controls.
- Use secure coding practices.

### Detecting XXE Attacks on Logs
- Search for specific keywords
   - DOCTYPE
   - ELEMENT
   - ENTITY
   - Can use a regex like: ^(\S+) - (\S+) \[(.*?)\] "(\S+) (.*?)\?(?=.*?\b21DOCTYPE\b).*? HTTP\/\d\.\d" (\d+) (\d+) "(.*?)" "(.*?)"

The questions below refer to the attached access log file.

#### Q1: What parameter affected XXE?
<pre>data</pre>
This can be found by searching for specific keywords commonly found in XXE attacks (i.e., DOCTYPE)

<br>

#### Q2: What file did that attacker try to read using XXE?
<pre>/etc/shadow</pre>
You can find this in the web requests where XXE is being used.
<br>

#### Q3: What was the attacker's IP address?
<pre>94.23.33.25</pre>
