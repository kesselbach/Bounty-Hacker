# The TryHackMe box 'Bounty Hacker' created by Sevuhl
# ![Alt text](images/9ad38a2cc31d6ae0030c888aca7fe646.jpeg?raw=true "Title")
+ **We deploy the machine and start with an nmap scan for open ports**


``nmap -sV -sC -oN scan1 10.10.229.13``
      
+ **We can see 3 open ports with some well known services: ftp, ssh and http, all opened on default ports**

![Alt text](images/nmap_scan.jpg?raw=true "Title")

+ **Next, we will try to connect to the ftp service using the default user anonymous**

![Alt text](images/ftp_login.jpg?raw=true "Title")

+ **Listing the directory, we can observe two .txt files uploaded so let's get them**



``mget *.txt``



        
