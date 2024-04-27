# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
## OUTPUT:
![1](https://github.com/Nandhinijaya/Metasploit-for-reconnaissance/assets/121998147/7c7815d7-ba01-4211-81f1-9f2d517c6600)

Invoke msfconsole:
![haa](https://github.com/Nandhinijaya/Metasploit-for-reconnaissance/assets/121998147/5d24f63a-ef14-4418-93e8-0beb8492ebd4)
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![3](https://github.com/Nandhinijaya/Metasploit-for-reconnaissance/assets/121998147/be282796-aec4-4f7d-b549-89eb65104b2e)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000 OUTPUT:

![5](https://github.com/Nandhinijaya/Metasploit-for-reconnaissance/assets/121998147/4b1bd531-7d2d-4272-b6c0-7ed00f8e7afa)

db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24 OUTPUT:
![6](https://github.com/Nandhinijaya/Metasploit-for-reconnaissance/assets/121998147/76ffc805-92d4-435d-aeee-53d347ccaac9)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

![7](https://github.com/Nandhinijaya/Metasploit-for-reconnaissance/assets/121998147/b0c79c2c-2d9f-4ea0-a8e0-79a6e0a09462)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

The info command provides information regarding a module or platform,

OUTPUT:

![8](https://github.com/Nandhinijaya/Metasploit-for-reconnaissance/assets/121998147/f779dc6a-d6c7-4f6f-a235-7428f3758591)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init

MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![9](https://github.com/Nandhinijaya/Metasploit-for-reconnaissance/assets/121998147/3db2e11f-2611-4933-99c2-f687f6ee8c3f)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![10](https://github.com/Nandhinijaya/Metasploit-for-reconnaissance/assets/121998147/b2593591-2e30-472c-9c4a-556bdab6305f)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
![11](https://github.com/Nandhinijaya/Metasploit-for-reconnaissance/assets/121998147/170557ae-e22f-48fd-8eb5-91ab35390993)


Use the set rhosts command to set the parameter and run the module, as follows:
![12](https://github.com/Nandhinijaya/Metasploit-for-reconnaissance/assets/121998147/caf6e71a-d084-4434-8cd3-6f048b414575)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![13](https://github.com/Nandhinijaya/Metasploit-for-reconnaissance/assets/121998147/57f2dd80-e706-4291-ad5f-4db50faeeda3)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![14](https://github.com/Nandhinijaya/Metasploit-for-reconnaissance/assets/121998147/0f1bb967-c149-4aa8-8d52-876560d8c858)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
