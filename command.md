dmesg
this command will display kernel log messages, if you are having any issues with kernel, boot process, kernel drivers this will help to troubleshoot.

udevadm
this command queries udev device db and gets us info related to mounted devices
udevadm info --query-path --name=/dev/sda1 #gets info related tp /dev/sda1

lsblk
lists all block devices mounted onto system

du -sh #lists size of file in human readble format

Storage and file management

lsblk #lists all disks attached
df -h #lists all disks along with mount points and storage used
blkid #lists id for disk

Networking:
