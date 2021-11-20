# ETBD-OSEP
Notes Template/Checklist for PEN-300 OSEP

The Offensive Security PEN-300 Evasion Techniques and Breaching Defenses course teaches students how to gain intial entry to target networks thru client side attacks and basic web or SQL exploitation. The course focuses heavily on the lateral movement and privilege escalation thru the internal network utilizing Antivirus evaison and application whitelisting bypasses. It includes modules on linux and winodws privilege escalation and latermovement, Active Directory pivoting, SQL server pivoting, and process injection/process hollowing. The course prepares you to take the Offensive Security Experienced Penetration tester exam, a 48-hour exam where you must compromise and move laterally thru a complex network. The below template is a method for organizing notes on the target environments during the labs and exam and servers as a checklist for finding and exploiting vulnerabilities.

The first portion is for the target enivronment to organize a list of target machines and their details, passwords/hashes that can be reused in the traget network, domain names and indetifiers, which machine is being used to route into the internal network, and maps of interdependencies and links. The second protion is specific to a target machine to required the details found and a check list to help jog the memory on what to look for. The last portion is a place to copy and paste the various payloads you have built and used thru out the course so they are available for reuse (note you may need to change the shell code if your IPs have changed).

There will probably be additional updates to the list later. This is not designed to give you the answer but to help you organize your notes and help you remember what to look for. You can adapt the various questions to be more specific and include exact commands to run.

Environment specific: 
- Host list:
- 	IP:	Name:	Service/Role:
- Credentials harvested:
- hashes dumped:
- Domain names:
- Domain SIDs:
- Non-default domain groups and their members:
- Machine use to route and proxy to internal network:
- BloodHound maps to targets:

Target specific: 
- Machine Name:
- IP:
- OS:
- Initial Foothold:
- Privilege Escalation:
- NMAP results:
 
- Webserver:
	- • dirb results:
	- • nikto results:
	- □ Can you upload anything that will provide a shell?
	- □ Are there any e-mail addresses listed that can be used to e-mail a client-side attack?
	- □ SQL injection: 
		-  Can you dump credentials? 
		-  Can you get a reverse shell?
	-  □ Command injection:

- SQL Server:
	- □ enumerate DB users
	- □ Can you impersonate a user with higher privileges?
	- □ Linked servers?
	- □ Can you enable running system commands?
	- □ Can you connect to an SMB share?
	- □ Can you relay NTLM or pass the hash?
	- □ Can you dump credentials?
	- □ Can you run queries on the linked servers to do any of the above?
	- □ PowerUpSQL:
		- Can you escalate privileges?
		- Can you query linked servers for lateral movement?

- Windows:
	- □ What user account are you?
	- □ What groups is it a member of?
	- □ What privileges exist?
	- □ Impersonate?
	- □ Are there scripts ran as admin that can be edited?
	- □ Can any services be edited?
	- □ Write permissions on an executable ran as system?
	- □ passwords stored in scripts?
	- □ Is user a LAPS password reader?
	- □ dump hashes?
	- □ Dump SAM/SYSTEM?
	- □ RDP files with passwords stored?
	- □ Dump LSASS?
	- □ pull clear text passwords with mimikatz?
	- □ SSH private key files?
	- □ Any unusual open ports for communications to uncompromised machines?
	- □ AMSI bypass:
		- turn off A/V or remove definitions?
		- PowerShell AMSI bypass techniques?
	- □ Application whitelisting bypass:
		- Trusted folders?
		- Alternate Data streams?
		- python?
		- Constrained Language Mode bypass?
		- Jscript/MSHTA?
		- installutil?
	- □ Domain enumeration/lateral movement:
		- Who are domain admins and enterprise admins?
		- Any server or workstation admin groups and who are the members?
		- Identify all servers and workstations, list out by role (i.e. file, web, mail, sql, etc.)
		- DNS zone transfer?
		- Is LAPS enabled and who are the readers?
		- Generic ALL or Generic Write on a user or computer object?
		- Do you have permissions to change another users password?
		- Are there any forest trusts?
		- Is SID history enabled on forest trusts?
		- Unconstrained delegation?
		- Constrained delegation?
		- Resource Based delegation?
		- Any users that are members of groups in a different domain?
		- Is a user you control a member of a group that would have permissions on an uncompromised machines (based off of group name and target machine names/functions)?
		- Password reuse (includes hashes)?
		- Can you capture a ticket for pass the ticket?
		- Can you copy a file to a remote target?
		- Can you create/modify/start a service on a remote target?

- Linux:
	- □ What user are you?
	- □ Can you sudo with or without password?
	- □ If user can sudo anything without password can it be exploited to get a shell?
	- □ Any active SSH sessions?
	- □ ControlMaster?
	- □ SSH-Agent forwarding?
	- □ SSH private keys?
	- □ Does SSH private key have a password and if so can you crack it?
	- □ Any scripts or files contain passwords?
	- □ Cron jobs?
	- □ Can any config files be edited to establish backdoors?
	- □ Hijack shared libraries?
	- □ Exploit LD_PRELOAD?
	- □ Ansible:
		- Can you run commands on a target?
		- Can you edit or create a playbook to run on a remote target?
		- Is there a privileged user password in a play book?
		- Can you crack an ansible password vault hash?
		- Can you pull clear text passwords from logs?
	- □ Artifactory:
		- Can you login?
		- Are any users downloading binaries from other target machines?
		- Can you replace a binary for a target to download?
		- Can you pull password hashes from backups?
		- Can you crack that hash?
		- Secondary Admin?
		- Pull hashes from database?
	- □ Kerberos:
		- Any tickets available with klist?
		- Any users in /home that appear to be windows domain users?
		- Any krb5cc_ files (may need to ssh in, sometimes it doesn't show up in meterpreter shell)?
		- Any keytab files?

Payload section:
- A/V evasion:
	- □ payload obfuscation - encoding and ciphers or shell code:
	- □ emulation bypasses (sleep or non-emulated API calls):
	- □ obfuscate variables and function parameters:
	- □ Does your payload/macro work on the development machine with defender on?
	- □ process injection:
	- □ process hollowing:
	
- reverse shells:
	- □ msfvenom payload:
	- □ PowerShell:
	- □ python:
	- □ C:
	- □ C#:
	- 
![image](https://user-images.githubusercontent.com/84335647/142711533-bf369919-6080-48b5-ae21-a62f628e6fee.png)

