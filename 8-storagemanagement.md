Block Storage: Data is read or write in blocks, 
lsblk # lists all block devices
fdisk is used to list all partitions, also you can use to do partitons
gdisk # this is also used to partion disk

DAS:
Storage directly connected to a server/computer (like USB drives, internal/external disks)
Access level: Block, File
Speed: High
SAN:
A high-speed network that connects servers to block-level storage over protocols like iSCSI or Fibre Channel
Access level: Block
Speed: High
NAS:
A dedicated storage device connected to a network and accessed via file protocols (like NFS, SMB)
Access level: file
Speed: Moderate

NFS:
client: that uses storage
server: that provides storage
the server has /etc/exports file that expose directory to a particular set of servers like this 
/dev/data 10.11.20.25 10.11.20.26 10.11.20.27 

meaning /dev/data in nfs server is exposed to 10.11.20.25,26,27 servers they can use this folder to read or write data based on permissions provided

there may be a firewall between client and servers which needs port to be exposed to work 

once /etc/exports file is done run 
exportfs -a this exports filesystem to servers
on server create a directory and mount the filesystem on to that directory 
on client
mount nfsserver_ip:filepath directory
eg: mount 10.11.20.11:/dev/data /mnt/data


LVM:
lvm is used to manage volumes/hard disks on the computer.
you have a 100GB disk attached to your server, using lvm you can manage the disk by lvm or you have 3 seperate disks attached each 30GB, you can manage 90GB using 1 LVM
1. install lvm
2. create phyisical volume or pv
   pv create /dev/sdb
3. create volume group 
   vgcreate  myvg /dev/sdb
   pvdisplay #to display details of pv
   vgdisplay #to display details of vg
4. lvcreate -L <size> -n <name to logical volume> <name of volumegroup created in step 3 myvg>
   lvcreate -L 1G -n dev myvg
5. create filesystem
    mkfs.ext4 <lv path>
6. create a directory and mount this file system
    mount -t ext4 <fs path> <directory created>
7. to resize 
   lvresize -L +1G <path to lv>
    now resize filesystem
    resize2fs <path to lv>
 
if you are using mount -t mention type of filesystem like ext4 or ext3 
if you are mounting nfs use mount -t nfs 



