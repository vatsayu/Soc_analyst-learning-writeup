# Information Gathering
- Attackers use a technique called spoofing to make user believe incoming info is reliable.
- SPF, DKIM, and DMARC protocols are used to determine whether sender address is fake or real.
  - SPF: Sender Policy Framework.
  - DKIM: DomainKeys Identified Mail.
  - DMARC: Domain-based Message Authentication, Reporting, and Conformance.
- Can determine if mail is spoofed or not by using tools such as Mxtoolbox.
- Notable Email Parameters
  - Sender Address (info@letsdefend.io)
  - SMTP IP Address (127.0.0.1)
  - @letsdefend.io (domain base)
  - Subject
 
<br>

# What is an Email Header and How to Read Them?
- Header is a section of an email.
- Contains info such as sender, recipient, and date.
- Allows you to identify sender and recipient
  - i.e., Use From and To fields.
- Block spam emails based on header analsyis.
- Check email route.
### Important Fields
- **From**
- **To**
- **Date**
- **Subject**
- **Return-Path**: Aka Reply-to. Reply is sent to address specified in Return-Path field.
- **Domain Key and DKIM Signatures**: Help email service providers identify and authenticate emails.
- **Message-ID**: Unique identifier for emails.
- **MIME-Version**: MIME converts non-text content into text so they can be attached in emails.
- **Received**: Lists each mail server passed before inbox.
- **X-Spam Status**: Show spam score of email.

<br>

#### Q1: If we wanted to respond to this email, what would be the recipient's address?
<pre>info@letsdefend.io</pre>
View source on the email. If responding to this email, you would refer to the email specified in the From field.

<br>

#### Q2: What year was the email sent?
<pre>2022</pre>
Date is found in the Date header in View Source.

<br>

#### Q3: What is the Message-ID? (without > < )
<pre>74bda5edf824cea8aad36e707.675c34a61f.20220321204512.a02caaccf3.a268ce5a@mail41.suw13.rsgsv.net</pre>
The Message-ID can be found in View Source.

<br>

# Email Header Analysis
- Key questions to ask when checking headings during phishing analysis:
  - Was email sent from correct SMTP server?
  - Are data in "From" and "Return-Path / Reply-To" the same?

<br>

#### Q1:  Question: Are the sender’s address and the address in the “Reply-To” area different?
<pre>Y</pre>
<br>

#### Q2: If I want to reply to this email, which address will it be sent to?
<pre>mrs.dara@daum.net</pre>
This is based on the Reply-To header field.
<br>

#### Q3: What IP address was the email sent from?
<pre>222.227.81.181</pre>
In View Source, "google.com: domain of mrs.dara@jcom.ne.jp designates 222.227.81.181 as permitted sender"

<br>

# Static Analysis
- Attackers can use HTML to hide malicious URLs.
- VirusTotal can be used to query if web address is harmful.
  - Ensure to rescan as security analysts can be fooled into thinking its harmless.
- Cisco Talos Intelligence can be used to learn reputation of IP addresses.

<br>

# Dynamic Analysis
- Website and files in mail should be run in sandbox environments to determine if they are harmful or not.
- Can use web browsers like Browserling to check web addresses in email.
  - Should be safe - not visiting website on your own computer.
  - Cannot run malicious file.
- Important to hover over URLs for important info.
- Commonly used sandboxes:
  - VMRay
  - JoeSandbox
  - AnyRun
  - Hybrid Analysis (Falcon Sandbox)
