Ubuntu based package Managers:
dpkg: cant handle dependencies, let us assume you are installing git and it needs other softwares as dependencies, dpkg cant install those.

-i install 
-r remove
-l list
-s show status
-p path to file
apt-get: can install dependencies, used for automations and scripting 
/etc/apt/repos.list  #list repos

apt: can install dependencies, used for manual user interactions for software packages installations.
apt update 
apt upgrade
apt install
apt remove
apt search

RHEL based package Managers:
rpm: file extension for package manages by rpm is .rpm, cant handle dependencies
-i install
-e uninstall
-q query
-U upgarde
-V verify

yum: handles dependencies
/etc/yum.repos.d  stores details of repos
.repo extension

there may be cases where you want to install a package suppose nginx and that package is not provided in by official package manager, then you can create a file called nginx.repo inside /etc/yum.repos.d like /etc/yum.repos.d/nginx.repo and you can mention your config there

yum install 
yum remove
yum upgrade
yum provides scp #suppose you dont what package provides scp you can check using provides
yum repolist #lists all repos

dnf: good for scripting, and handles dependencies
