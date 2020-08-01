# The TryHackMe box 'Bounty Hacker' created by Sevuhl
# ![Alt text](images/9ad38a2cc31d6ae0030c888aca7fe646.jpeg?raw=true "Title")
+ **We deploy the machine and start with an nmap scan for open ports**


``nmap -sV -sC -oN scan1 10.10.229.13``
      
+ **We can see 3 open ports with some well known services: ftp, ssh and http, all opened on default ports**

![Alt text](images/nmap_scan.jpg?raw=true "Nmap_scan")

+ **Next, we will try to connect to the ftp service using the default user anonymous**

![Alt text](images/ftp_login.jpg?raw=true "Ftp_login")

+ **Listing the directory, we can observe two .txt files uploaded so let's get them**



``mget *.txt``

+ **Reading the task.txt file, we can find out who wrote the task list, giving us the first task answer. We list the second txt file, named locks.txt, and we can see multiple strings which seems to be some passwords kept in the ftp server**

```
rEddrAGON
ReDdr4g0nSynd!cat3
Dr@gOn$yn9icat3
R3DDr46ONSYndIC@Te
ReddRA60N
R3dDrag0nSynd1c4te
dRa6oN5YNDiCATE
ReDDR4g0n5ynDIc4te
R3Dr4gOn2044
RedDr4gonSynd1cat3
R3dDRaG0Nsynd1c@T3
...
```

+ **Let's try to use this password file to connect on the ssh service, using simultanously the user found in the previous task. The Hydra tool has a brute-force option to crack the login of the ssh service, so we can use it**

``hydra -l lin -P locks.txt 10.10.229.13 -t 4 ssh``


+ **After we execute the brute-force process, Hydra give us the needed user password**

# ![Alt text](images/hydra_brute.jpg?raw=true "Hydra")

+ **With the given credentials, we will connect to the ssh service**

``ssh lin@10.10.229.13``

+ **We land on the wanted system so we can read our first user flag**

# ![Alt text](images/first_flag.jpg?raw=true "first_flag")

+ **Running the** ``sudo -l`` **command on @lin user and listing the allowed commands, we can see that user @lin may run the following commands on bountyhacker:**
      ``(root) /bin/tar``
  
# ![Alt text](images/whoami.jpg?raw=true "whoami")




        
