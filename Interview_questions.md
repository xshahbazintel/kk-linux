what is a login and non login shell?
Login shell is the shell given to the user you login 
let us assume you are bob and you want to swith user as brad, bob home directory is /home/bob and brad is /home/brad

you do su - brad
now you will login to the shell as regular user brad and all the environment variables will be applied in the brad profile and your home directory will also changed to /home/brad and your previously executed commands are not shown 

this will reads .bash_profile (for RHEL based systems mostly) or .profile(for ubuntu based systems mostly)

you do su brad 

now from your shell you are changed to brad, but you home directory is still /home/bob and env variables of brad is not applied, and your previously applied commands are still present and it doesnt reset the terminal.

loads .bashrc



/etc/profile system will loads this what ever login type you use
.bash_profile #load this profile when you are using an login shell and shell used is login
.profile # used for non bash shells 

#these are used when you are using non-login shells
/etc/bash.bashrc  #for system wide users
~/.bashrc  #for user specific

