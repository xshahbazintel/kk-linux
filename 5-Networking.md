Imp Files:
/etc/hosts
let us assume you have a  server 192.168.10.11 and you want to ping it with name instead of ip address, if you dont have dns resolver you can keep hostnames here

192.168.101.11 db # this will blindly belives that 192.168.101.11 as db even it has a different hostname, you can even make it to believe 192.168.101.11  as www.google.com

/etc/resolv.conf # the place for configuring your dns server 
nameserver <ip address of dns server>  #this will be your dns server ip address
when you try to ping with hostname and entry is not present in /etc/hosts it will look for dns server and try to resolve from there

/etc/nsswitch.conf #this is the place where you configure the order to check for dns resolving whether it has to look for /etc/hosts file first or dnsserver first 
hosts: dns files  #dns first means look for dns server first for host name resolutoion followed by /etc/hosts

hosts: files dns #look in /etc/hosts first if not found look in dns server

let us assume you are working in an org called intel, you have domain name as intel.com, you want to ping ba.intel.com, how do you you are ping with ping ba but you want to resolve it as ba.intel.com

in /etc/resolv.conf add a field called 
search intel.com dev.intel.com qa.intel.com 
when you do ping with ping ba
this will try to resolve with ping ba.intel.com if found ok, else continues with ping ba.dev.intel.com like this 



switch: delivers packet from one system in network to another system in same network
ip link #shows list of interfaces
switch has an ip address 192.169.1.0, this will resolve ip address for systems in same network
in system 1 do 
ip addr add 192.168.1.10/24 dev eth0  #this is saying that for ip addresses in range 192.168.1.0 to 192.168.1.255 forward that to device eth0 as a route 

do the same in system 2 

to list all the routes run 

route or ip route 

we have 1 network at 192.168.1.0/24 and 1 network at 192.168.2.0/24

to forward traffic between these 2 networks you need a router 

in router connect one end to 1st switch port and one end to switch port of 2nd network 

do 

ip route add 192.168.1.0/24 via 192.168.2.1 this is saying that to forward traffic to 192.168.1.0/24 use 192.168.2.1 of router, this is the port that is connected to router for 2nd network





