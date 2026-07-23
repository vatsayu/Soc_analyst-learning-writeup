- Splunk is a data platform.
- Need to open the following ports on firewall:
	- `9997` - Splunk indexer
	- `8000` - For clients to Splunk search page
	- `8089` - splunkd (used by deployment server)
- Free trial is 60 days.

#### Q1: How many days do you have for the free trial?
```
60
```

## Splunk Installation on Windows
- Splunkd is a service that starts up automatically.
	- Indexing and searching engine.

#### Q1: What's the service display name for Splunk on Windows?
```
Splunkd Service
```

## Splunk Installation on Linux
#### Q1: Which command to check the Splunk status on Linux?  
  
Answer Format: /x/x/x/x status  
  
Note: You must answer according to this lesson's installation instructions.
```
/opt/splunk/bin/splunk status
```

#### Q2: Does Splunk start on Linux startup by default?  
  
Answer Format: Y/N
```
N
```
On Linux, you have to start Splunk manually. To automatically start at boot run the following command `/opt/splunk/bin/splunk enable boot-start`

## Splunk Universal Forwarders
- A deployment server is a server that can send a configuration for universal forwarder.
	- Not needed. A receiving indexer (server that has Splunk installed) will suffice.
- To check if Splunk Universal Forwarder communication is open, enter the following command in PowerShell:
	- `Test-NetConnection -Computername Splunk_IP -port 9997`
	- Change Splunk_IP according to your setup.

## Add Data to Splunk
1. Settings -> Add Data
2. Select "Forward" at bottom.
3. Select a host and give a server class name.
4. Select what you want to monitor (i.e., Local Event Logs).
5. Select index (where logs will be).
- You can also upload logs (i.e., csv).
### Add Receiver
1. Setting -> Forwarding and receiving.
2. Add new receiving.

## Search on Splunk
<img src="https://ld-images-2.s3.us-east-2.amazonaws.com/Splunk/images/mode2.png"/>

The questions below require you to start up a LetsDefend machine (for Splunk), download and upload the data file to Splunk.

#### Q1: How many different client IPs are there requesting the "/productscreen.html" path?
```
65
```
Select field `uri_path` and filter with `/productscreen.html`. If you look on the left side, the `clientip` field shows 65 - number of different client IPs requesting the path.

#### Q2: What is the path where the client IP address "128.241.220.82" sends the most web requests?
```
/cart.do
```
Apply the filter of `clientip = "128.241.220.82"` and click on `uri_path` field to check paths that the client requested. `/cart.do` has the highest number of requests for this client.

## Creating and Managing Splunk Reports
- Reports are saved search results - can be scheduled or executed when needed.
#### Q1: Can you send an email when a report is generated?
```
Y
```

## User Management on Splunk
- Good practice is to create another administrator account and use admin only in emergency cases.
#### Q1: How many users do we have on our Splunk?
```
1
```
This is referring to our deployed Splunk instance. You can find users at `Settings -> Users`.

#### Q2: How many roles do we have on our Splunk?
```
5
```
Can be found at `Settings -> Roles`
