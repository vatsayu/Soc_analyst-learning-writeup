## Brute Force Attacks
- Brute force is any activity performed to find a username, password, directory, or encryption key using trial and error method.
### Online Brute force attacks
- Attacker and victim are online at same time.
- Can be categorized as Passive or Active:
	- Passive
		- Attacker and victim do not directly communicate with each other.
		- Both are on same network.
		- Examples: Man in the middle, sniffing.
	- Active
		- Attacker communicates directly with victim.
		- Useful for simple passwords.

### Offline Brute force attacks
- Used for captured encrypted or hashed data.
- Password info can be obtained in the following ways:
	- Capturing packets on wireless networks.
	- Dumping hashes from db with SQLi (SQL injection) weakness.
- Carried out in 3 different ways: Dictionary attacks, brute force attacks, rainbow table attacks:
	- Dictionary Attacks
		- Problem caused by use of common password.
		- Each word in dictionary tested on target system as password.
	- Brute force attack (self-explanatory)
	- Rainbow Table Attacks
		- Password possibilities are calculated using a function.
		- Compares pre-calculated hash file with password summary (if there is a match).
		- Problem is high processing power and disk space requirement.

#### Q1: What is the name of the password cracking method that uses a pre-calculated hash table to crack the password ?  
  
Answer format: **XXXX XXXX** attack
```
rainbow table attack
```

## Protocol/Services That Can Be Attacked by Brute Force
- Login pages
- RDP
- SSH
- Mail server
- LDAP
- Database services
- Web app home directories (directory brute force)
- DNS servers (dns brute force)

#### Q1: What is the name of the attack that the attackers usually made on the protocol running on port 22 in order to obtain a session on a linux server?
```
SSH brute force
```
SSH uses port 22, so the attack described in this case is SSH brute force.

## Tools Used in a Brute Force Attack
- Aircrack-ng
	- 802.11a/b/g WEP/WPA cracking program.
	- Recovers a 40/104/256/512 bit WEP key once encrypted packets gathered.
- John the Ripper
	- Helps system administrators find weak passwords.
	- Can automatically mail users about weak passwords.
- L0phtCrack
	- Cracks Windows passwords.
	- Rainbow tables, dictionaries, multiprocessor algorithms.
- Hashcat
	- Supports five unique modes of attack for over 300 highly-optimized hashing algorithms.
- Ncrack
	- Crack network authentication.
	- Help companies secure their network by testing all hosts and networking devices for poor passwords.
- Hydra
	- Parallel login cracker which supports various protocols to attack.
	- Fast and flexible.

## How to Avoid Brute Force Attacks?
- Enforce use of strong passwords:
	- Never use info that can be found online (i.e., family names).
	- Many characters as possible.
	- Combine letters, numbers, and symbols.
	- Minimum 8 characters.
	- Each user account is different.
	- Avoid common patterns.
- Here's some ways to protect users as administrators of an organization:
	- Lock Policy
		- After certain number of failed attempts, lock accounts and unlock them as admin.
	- Progressive delays
		- Lock accounts for limited time after failed attempts.
		- Captcha-reCAPTCHA can be used to make it mandatory for users to complete simple tasks prior to logging in.
	- Strong Password Policy
	- 2FA

#### Q1: After logging in the username and password, what is the name of the method in which a second verification is made to the user with an additional verification mechanism (SMS, mail, token,push notification, etc.)?  
  
Answer format: XXX
```
2FA
```

## SSH Brute Force Attack Detection Example
- We can view machine logs to detect failed brute force attempts.
	- For example in Linux, you can check in the logs in `/var/log`
	- Use Linux command: `cat auth.log.1 | grep "Failed password" | cut -d " " -f10 | sort | uniq -c | sort`
	- Locate IP addresses: `cat auth.log.1 | grep "Failed password" | cut -d " " -f12 | sort | uniq -c | sort`
	- Successful logins: `cat auth.log.1 | grep "Accepted password"`

## HTTP Login Brute Force Attack Detection Example
- Relevant logs on web server should be examined for brute force attacks.
- Take note of the difference in response sizes when comparing failed and successful login attempts.
	- If short response size -> successful
	- If large response size -> unsuccessful

## Windows Detection Login Brute Force Detection Example
### Windows Login Records
- Need to find the Event ID and login dates.
- Open Event Viewer -> Security
- Filter by event ID.
	- An event ID of 4624 indicates a user successfully logged on.
- Check the Logon Type field - a value of 10 indicates remote login.
#### Q1: What is the event id value that indicates that the user is successfully logged in to a Windows system?
```
4624
```

- Wfuzz does not support RDP brute force attacks.
	- Web content scanner.
	- Performs complex web security attacks.
