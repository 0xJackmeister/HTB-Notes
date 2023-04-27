```
smbclient //querier.htb/reports

python3 olevba.py ~/htb/querier.htb/Currency\ Volume\ Report.xlsm

#found this sus string
conn.ConnectionString = "Driver={SQL Server};Server=QUERIER;Trusted_Connection=no;Database=volume;Uid=reporting;Pwd=PcwTWTHRwryjc$c6"

reporting : PcwTWTHRwryjc$c6

```
