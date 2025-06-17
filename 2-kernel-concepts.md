Kernel acts a bridge between software and hardware to manage resources

kernel keeps a track of these components
1. Memory Management: keeps a track of memory used
2. process Management
3. Device Management
4. system calls and security

kernel is monolithic and modular

How to check a kernel version?
uname will have details of system, bu running uname command you can check which kernel is system using, uname -r will give details of kernel version

kernel is like a librarian in a library, when you want a book you you get a reservation from librarian, he keep track of records, lease etc, similarly kernel allocates resources.
there are some spaces where only librarian can access similar to this in kernel are called as kernel space
Kernel Space: where only kernel will have access, kernel runs it code and resources here, kernel has unlimited restrictions on hardware here.
UserSpace: This is the place where applications, programs runs.

The application in userspace will make a call to kernel, the kernel then processfullfills the request by contacting the hardware and allocate space or memory to that resource.

when you mount a device like external harddisk to system, kernel detects it and in kernel space device driver sends an event called uevent to userspace device manager called udev, udev is responsible for dynamically creating a device node called /dev/sda1

Boot Process:
The boot process has 4 steps
1. BIOS POST: BIOS will run Power On Self Test, this will check if all hardware are functioning properly.
2. BootLoader: Once POST is passed, now bios will look for MBR, once MBR is found it will start booting from boot code which is located on first sector of harddisk. The boot loads kernel into memory and handover the control to kernel.
Eg of bootloader: GRUB2
3. Kernel initilisation: Kernel is loded into memory and starts tasks like init hardware and memory management, once it is completely operational it will looks for init process.
4. Init Process: Init process will look for system daemon also called as systemd, this systemd is reponsible for mounting file system, and starts system process.
to check what init system is used 
ls -l /sbin/init

Run Levels:
In linux based distros, some will get UI based login, some will get shell based login no GUI
this is decided by run level set during system load 
is run level is 3 or multiuser.target then system load in shell level
if run level is 5 or graphical.target then system loads in GUI mode

to check this run 
systemctl get-default  # gets the run level set
systemctl set-default multiuser.target #changes the run level set


Runlevel	systemd Target	Description
0	poweroff.target	Shutdown system
1	rescue.target	Single-user mode
2, 3, 4	multi-user.target	Multi-user (text-mode)
5	graphical.target	Multi-user + GUI
6	reboot.target	Reboot the system


File Types in Linux:
Every thing is file in linux
regualar files: jsut like documents, txt, bash scripts
directory: directories is also a special type of file
special files: charachter files: like mouse, keyboards, block files like mounted hard disks, links like soft and hard links, socket files and pipes which are used for input and output redirection.

File hirearichy:
/home user home directories
/var  log files
/etc  config files
/opt  3rd party packages
/mnt  mount points
/bin  binary files 
/dev  device mounts
/media media devices mounts

