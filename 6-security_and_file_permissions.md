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
