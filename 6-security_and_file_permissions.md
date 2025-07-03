user:
to check users details 
id #this will give details for user like group he is part of 

useradd <name of user>
passwd <name of user>  #to set passwd to user
userdel <name of user> # to delete user
useradd -u <uid> -g <gid> -d <user home directory> -s <default user shell> -c <any comments>

# manage groups
groupadd  -g <gid> <name of group>
groupdel <group name>



The details of sudoers is stored under /etc/sudoers

/etc/passwd #stores list of users with uid and gid homedir and default shell
/etc/shadow #stores passowrd details in encrypted format
/etc/group  #stores group details



file permissions:
- --- --- ---
first one denotes if its file or directory or socket or link or pipe or any other
next 3 for user denoted as u followed by group and others 
as u g o 
every of the 3 groups i.e u g o has read r, write w, and execute permissions
as 
drwxrwxrwx  
octal values: read has an octal value of 4, write has 2, execute has 1

if you are owner of the directory and part of group what permissions will apply?
first it will check who is trying to access if you are the owner of file or directory then user permissions will apply wont check for group permissions
if you are not the user then it will check who is the group owner for that file or directory and check if you are part of that group, if yes group permissions will apply else other permissions will apply 

chmod  #changes file permissions
chown  user:group file/directory changes owner and group for file or directory
chown user file/directory #changes owner of file or directory
chgrp #changes group ownership of file or directory

SSH:
ssh service should run on machine
user you are trying to login to machine should be present in machine

#generate ssh key pair
ssh-keygen -t rsa # this will generate an id_rsa.pub and id_rsa in users home directory .ssh folder

to copy public key to target machines .ssh/authorised_keys you can use

ssh-copy-id  <target_machine>


scp:

scp <local file path> <target-machine>:<path>
scp /home/bob/app.jar prod-server:/app/


IP Tables:
iptables -L #lists firewall rules
this has 3 rules
INPPUT: that accepts incoming trafic to server 
OUTPUT: that initiates output traffic from server
FORWARD: forwards the traffic
Evaluates rules from Top to Bottom

# TO ACCEPT AN INCOMING CONNECTION FROM SERVER ON PORT 80 FROM 172.16.238.187
iptables -A INPUT -p tcp -s 172.16.238.187 --dport 80 -j  ACCEPT
# tO DROP ALL INCOMMING CONNECTIONS, THIS SHOULD BE LAST 
sudo iptables -A INPUT  -j DROP

CRON JOB:
crontab -e #add new cron
crontab -l #list cron job 

check /var/sys/log for any failures



