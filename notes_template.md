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
