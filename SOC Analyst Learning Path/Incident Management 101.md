## Basic Definitions About Incident Management
- Alert - Generated message as a result of data collection and processing.
- Event - Observable occurrence.
- Incident - Violation of computer security practices.
- True Positive - Condition you want to detect (i.e., if account was compromised) and detected condition (i.e., account indeed was compromised) are the same.
- False Positive - False alarm.

#### Q1: A web attack alert has occurred because I have logged into the following URL address. Is this alert a false positive or a true positive?  
  
https://www.w3schools.com/sql/trysql.asp?filename=trysql_select_union3
```
False positive
```
Domain name does not appear to be suspicious, so false positive.

## Incident Management Systems (IMS)
- SOC teams conduct investigation process and record actions taken when incident occurs.
- Example: TheHive project.
### How IMS works?
1. Data entry must be provided.
2. Ticket/case created.
3. Integrations with threat inteligence or SOAR helps respond quickly to incidents. Otherwise, manual query (i.e., VirusTotal).
4. Alert closed when operations are complete.

#### Q1: Which button in the “Investigation Channel” should we click to open a record on “Case Management” on the LetsDefend platform?
```
Create Case
```

#### Q2: Which is not a feature of the Incident Management System  
  
- Workflow  
- Automation / API access  
- Close, open, edit action  
- Prevention
```
Prevention
```
All except prevention is what IMS are capable of. (I mean what's the point of managing an incident if its already prevented?)

## Case/Alert Naming
- Ticket/case/record titles should have meaningful names to help retrospective inquiries.
- Naming method for LetsDefend is as follows:
	- `EventID: {Alert ID Number} - [{Alert Name}]`
- Sometimes the following fields may be included:
	- Alert Category
	- Event Source
	- Description

#### Q1: The case/ticket format in LetsDefend is as follows:  
  
EventID: {Alert ID Number} - [{Alert Name}]  
  
According to this information, how can the ticket be created for the alert with ID number 25 and rule name "SOC15 - Malware Detected" be named?
```
EventID: 25 - [SOC15 - Malware Detected]
```

## Playbooks
- Playbooks are workflows for effective and consistent analysis of alerts.
- Playbooks provide guidance, especially to those that just started in the SOC field.

## What Does the SOC Analyst Do When An Alert Occurs?
- Most of time is spent dealing with false positives.
- Constant communication with team that creates SIEM rules and always provide feedback.
