## Network and Log Analysis
- Determine whether malicious URLs or malicious files were downloaded.
- Find IP address of affected host.
	- Navigate to Endpoint Security on LetsDefend and search for hostname.
	- Review host information.
		![[Pasted image 20250710105820.png]]
- Navigate to Log Management and search using the IP address obtained previously.
- Identify suspicious connections (focus on source and destination addresses).
- Compare the time when alert was generated to log event times.
- The user Felix interacted with a destination IP of 37.120.233.226 and destination port 3451.
### Threat Intel
- Navigate to Threat Intel tab on LetsDefend.
- Consolidates threat intelligence data for investigations.
- Type suspicious IP or URL you found in log management.
	- LetsDefend will query if IOC is associated with any malicious activity.

The following questions correspond with the alert associated with this lesson.

#### Q1: What is the IP address of the Felix host?
```
172.16.20.151
```

#### Q2: When exactly did Felix download the malicious file?
```
May, 13, 2024, 12:59 PM
```

#### Q3: What is the C2 address?
```
37.120.233.226
```

#### Q4: What’s the name of the process that communicated with C2?
```
coffee.exe
```

#### Q5: What port did the malware use to communicate?
```
3451
```

## Endpoint Log Analysis
- Examine processes and browser activity on endpoints to identify IoCs.
- Navigate to Endpoint Security on LetsDefend.
### Process and Network Action Analysis
- Check list of running processes.
- Examine parent and child processes.
- Analysis suspicious process hash on threat intel platforms.
- Check network activity.
- Note any unusual inbound or outbound connections.
- Cross-reference IoCs on threat intel platforms.

### Felix - Endpoint Security Processes & Network
- Event Time: May 13 2024 13:00:38
- Process ID: 6697
- Image Path: "C:\Users\Felix\Downloads\Coffee.exe"
- Parent Process: explorer.exe
- Image Hash: CD903AD2211CF7D166646D75E57FB866000F4A3B870B5EC759929BE2FD81D334
- Network Action: May 13 2024 13:01:48; 37.120.233.226 (C2)

### Terminal and Browser History Analysis
- Terminal history allows us to see if there were suspicious commands executed on host.
- Browser history identifies any malicious websites or downloads.
- After analysis proceed with next step in playbook.

### Felix - Terminal and Browser History
- cmd.exe executed.
	- i.e., At May 13 2024 13:01:10, "C:\Windows\System32\cmd.exe" /c wmic logicaldisk get caption,description,providername
- Suspicious Amazon AWS URL was accessed.
	- 2024-05-13 12:59, files-ld.s3.us-east-2.amazonaws.com/59cbd215-76ea-434d-93ca-4d6aec3bac98-free-coffee.zip

### Containment
- Necessary to prevent data loss, unauthorized access, lateral movement, or data extortion.

The questions below correspond with the alert associated with this lesson.

#### Q1: What is the Process ID (PID) of the “coffee.exe”?
```
6697
```

#### Q2: What is the “image hash” of the malicious process?
```
CD903AD2211CF7D166646D75E57FB866000F4A3B870B5EC759929BE2FD81D334
```

#### Q3: How many child processes does “cmd.exe” have?
```
7
```
This can be found by filtering parent processes column with `cmd.exe`.

## Result
- Close the alert (Ensure you contained the host first!).
- State any artifacts.
	- i.e., Hashes, domains, URLs.
- Make a note (alert deemed a true positive).

#### Q1: On the monitoring page, through which channel can you access the official incident report of an alert?
```
Closed Alerts
```
