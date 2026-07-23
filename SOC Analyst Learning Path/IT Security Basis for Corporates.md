## Inventory
- Know what devices, applications, user permissions, and security controls are in place.
- Should include hardware, software, and date of report.
- Exclude equipment that is no longer maintained.
- Secure boot must be enabled on all compatible devices.
	- Ensures computer boots using manufacturer-approved software.
- Enforce strict policy regarding authorized and unauthorized software.
- GPO or Intune provides users with an available software library without needing administrative rights.
	- Saves time of installing software.
	- Reduces risk of downloading malicious program.
- Ensure software is forbidden - can be done through AppLocker or Intune.
- Hardening includes the following:
	- Station handover procedures.
	- Secure configuration device audit.
	- Configuration changes alerts.
	- Done through Ansible, GPO, or Intune.
- Deploy an antivirus or EDR starting with devices critical to business.

#### Q1: Which is not one of the issues to be considered while doing hardening work?  
Answer Format: X  
  
A) Station handover procedures with prerequisite checklist  
B) Audit of the secure configuration of the devices  
C) Alert in case of configuration modification  
D) Mouse movements of devices
```
D
```

## Backups
- Last line of defense.
### Rule 3-2-1
1. Have at least **three** copies of your data.
	Avoids backup failure.
2. Store on **two** different media.
	 Backup should be on two different and unrelated points (i.e., two copies of backup not stored in same datacenter).
3. **One** of which must be an offsite external backup.
	1 offline copy. 0 errors during restoration - regularly test backups if they can be made without errors.
### Minimum Storage Time
Backups allow to restore 30 days old data - average time between intrusion and detection by the company.

## Phishing Prevention
- Antispam and email protection.
- Phishing analysis procedure.
- Phishing drill - ensure staff are aware.
#### Q1: What is the simulation study done to raise awareness of corporate employees against phishing attacks?  
  
Answer Format: XXXX XXXX
```
phishing drill
```

## Internet Browsing Protection
- Filter connections to unauthorized websites, suspicious domain names, and malicious domain names.
	- Especially URL shorteners - massively used.
- Install plugins that disable automatic execution of content.
#### Q1: What should be done to block unwanted addresses to be accessed within the institution?  
  
Answer Format: XXX XXXX
```
DNS Filtering
```

## Patching
- Deploy patches as soon as possible.
- Service Level Agreement (SLA) - contract between service provider and customers - defines the standards provider is obligated to meet.

## Access Control
- Ensure only authorized users granted least privileges necessary.
- Passwords & MFA.
- Zero Trust - Identify and disable unused accounts, eliminate shared accounts.
- Analyze user activity for access attempts outside of business hours or unusual locations.
- No more than 15% of accounts should have domain administrator privilege.

## Risk Analysis
- Risk assessments help prioritize allocation of resources and investments.
- Estimate impact of disruptions and identify downtime.
- Review risks on connected networks.

## Network
- Monitor organization's incoming and outgoing Internet traffic.
- Use SPAN ports of network equipment to capture network activites.
- Network segmentation improves network performance and security by reducing attack surface and range of attack.
	- VLAN, PVLAN.
	- Review requests that get blocked - i.e., compromised workstation.
- Generate alerts in the event of abnormal network usage.
