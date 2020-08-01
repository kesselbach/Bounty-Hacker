# The TryHackMe box 'Bounty Hacker' created by Sevuhl
# ![Alt text](images/9ad38a2cc31d6ae0030c888aca7fe646.jpeg?raw=true "Title")
* **We deploy the machine and start with an nmap scan for open ports.**

      ``nmap -sV -sC -oN scan1 10.10.229.13``
      
* **We can see 3 open ports with some well known services: ftp, ssh and http, all opened on default ports. **

        
