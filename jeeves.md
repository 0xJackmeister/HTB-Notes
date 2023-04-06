```
gobuster port 50000 and get jenkins cms

use script console to execute groovy reverse shell and get user

whoami /priv
SeImpersonatePrivilege        Impersonate a client after authentication Enabled 

RottenPotato(msfconsole version) / JuicyPotato

#CLSID that work
{F7FD3FD6-9994-452D-8DA7-9A8FD87AEEF4}

#To check file hidden within file 
dir /r 

# example dir /r output
12/24/2017  03:51 AM                36 hm.txt
                                    34 hm.txt:root.txt:$DATA


#Possible command used to hide root flag
echo "userflag" > hm.txt:root.txt 

#echo file content into new file to read
more <hm.txt:root.txt> newroot.txt
```
