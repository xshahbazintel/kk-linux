How to attach a disk, create a file system and mount it?
create a file system, with out filesystem you can not use disk to read or write 

1. select the disk you want to create file system 
2. you can use 
   mkfs.<file system type to be used>  <block/partition>
   mkfs.ext4 /dev/sdb
3. Mount the file system on to directory, before this create directory where you want to mount
   mkdir /mnt/ext4
   mount /dev/sdb  /mnt/ext4
   the above commands wont persists if system reboots, insted of this you can create an entry in 
   /etc/fstab
   <device name> <mount path> <file extension type> <options> <dump> <pass>

   dump can be 0 or 1, 0 means do not backup using dump command, 1 means backup using dump command
   0: Do not back up with dump
   1: Include in dump backups
   pass can be 0 or 1 or 2 
   Value	Meaning
    0	Do not check this filesystem at boot
    1	Check first (usually used for the root / filesystem)
    2	Check after the root filesystem (all others)


1. create file system to disk or partition 
    mkfs.ext4 /dev/sdb
2. create a mount point
   mkdir -p /mnt/data
   mount /dev/sdb /mnt/data
3. create a entry in fstab for system reboots
   <device name> <mount path> <file extension type> <options> <dump> <pass>

How to format a disk using gdisk?
install gdisk
sudo gdisk <volume name>
sudo gdisk /dev/sdb
enter n 
select partition number if 1st select 1
enter 
select size if your disk is 1GB and you want to partition it to 500MB select 500MB
enter 
type w for saving 