Compressing and uncompressing files:
Compress files:
bzip2 <file/directory>  bunzip2 <file/directory>
gzip                    gunzip
xz                      unxz
Tar files:
tar -cf # -c create tar -f list of files or folder 
tar -xf # -x untar -f file to untar
tar -zf # compress the tar 
tar -tf #list files in tar

searching files and directories:
locate and find are used to search files
locate <file name>  #this will use a db to search if this db is not present run 
updatedb and run locate once again

find  <directory to find a file>  -name <file_name>
find /home/bob   -name city.txt   #returns citx.txt in all subfolders under /home/bob


Grep:
grep <text> <file>
grep -i #ignore case
grep -r <text> <folder>  #search recurcively for a text in a folder and subfolders
grep -w #searches for a particular word 

IO redirection:
python2 sample.py 2>/error.txt #redirects error to /error.txt
python2 sample.py 2>/dev/null #redirects error to a file /dev/null without printing on screen
