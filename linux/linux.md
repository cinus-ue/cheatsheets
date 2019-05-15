# LINUX COMMANDS CHEAT SHEET

## SYSTEM INFORMATION
```
$ uname -a    ---display linux system information
$ uname -r    ---display kernel release information
```

## HARDWARE INFORMATION
```
$ dmesg                       ---display messages in kernel ring buffer
$ cat /proc/cpuinfo           ---display CPU information
$ cat /proc/meminfo           ---display memory information
$ free -h                     ---display free and used memory
$ lspci -tv                   ---display PCI devices
$ lsusb -tv                   ---display USB devices
$ dmidecode                   ---display DMI/SMBIOS (hardware info) from the BIOS
$ hdparm -i /dev/sda          ---show info about disk sda
$ hdparm -tT /dev/sda         ---perform a read speed test on disk sda
$ badblocks -s /dev/sda       ---test for unreadable blocks on disk sda
```

## PERFORMANCE MONITORING AND STATISTICS

```
$ top                          ---display and manage the top processes
$ htop                         ---interactive process viewer (top alternative)
$ mpstat 1                     ---display processor related statistics
$ vmstat 1                     ---display virtual memory statistics
$ iostat 1                     ---display I/O statistics
$ tcpdump -i eth0              ---capture and display all packets on interface eth0
$ tcpdump -i eth0 'port 80'    ---monitor all traffic on port 80 ( HTTP )
$ lsof                         ---list all open files on the system
$ lsof -p pid
$ lsof -u user -c mysql
$ lsof -iTCP -sTCP:LISTEN
$ lsof -u user                 ---list files opened by user
$ free -h                      ---display free and used memory 
$ watch df -h                  ---execute "df -h", showing periodic updates
```

## USER INFORMATION AND MANAGEMENT
```
$ id                                ---display the user and group ids of your current user.
$ last                              ---display the last users who have logged onto the system.
$ last -F                           ---display complete login & logout times
$ last -x                           ---display last shutdown time
$ last -x shutdown 
$ who                               ---show who is logged into the system.
$ who -r                            ---display the current runlevel
$ who -a                            ---list logged in users
$ users
$ who -b                            ---display the time of last system boot
$ w                                 ---show who is logged in and what they are doing.
$ groupadd test                     ---create a group named "test".
$ useradd -c "content" -m test      ---create an account named test
$ userdel test                      ---delete the test account.
$ usermod -aG sales test            ---add test account to the sales group
```

## FILE AND DIRECTORY COMMANDS
```
$ ls -al                              ---list all files in a long listing (detailed) format
$ pwd                                 ---display the present working directory
$ mkdir dir-name                      ---create a directory
$ rm file                             ---remove file
$ rm -r dir-name                      ---remove the directory and its contents recursively
$ rm -f file                          ---force removal of file without prompting for confirmation
$ rm -rf dir-name                     ---forcefully remove directory recursively
$ cp file1 file2                      ---copy file1 to file2
$ cp -r source_dir destination        ---copy source_directory recursively to destination. 
$ ln -s /path/to/file linkname        ---create symbolic link to linkname
$ less file                           ---browse through a text file
$ tail -f file                     
```
## PROCESS MANAGEMENT

```
$ ps                        ---display your currently running processes
$ ps -ef                    ---display all the currently running processes on the system.
$ ps -ef | grep processname ---display process information for processname
$ top                       ---display and manage the top processes
$ htop                      ---interactive process viewer (top alternative)
$ kill pid                  ---kill process with process ID of pid
$ killall processname       ---kill all processes named processname
$ program &                 ---start program in the background
$ bg                        ---display stopped or background jobs
$ fg                        ---brings the most recent background job to foreground
$ fg n                      ---brings job n to the foreground
```
## FILE PERMISSIONS

```
Linux chmod example
        PERMISSION      EXAMPLE

         U   G   W
        rwx rwx rwx     chmod 777 filename
        rwx rwx r-x     chmod 775 filename
        rwx r-x r-x     chmod 755 filename
        rw- rw- r--     chmod 664 filename
        rw- r-- r--     chmod 644 filename

# NOTE: Use 777 sparingly!

        LEGEND
        U = User
        G = Group
        W = World

        r = Read
        w = write
        x = execute
        - = no access
        
    4 read (r)
    2 write (w)
    1 execute (x)

```

## NETWORKING

```
$ ifconfig -a          ---display all network interfaces and ip address
$ ifconfig eth0        ---display eth0 address and details
$ ethtool eth0         ---query or control network driver and hardware settings
$ ping host            ---send ICMP echo request to host
$ whois domain         ---display whois information for domain
$ dig domain           ---display DNS information for domain
$ dig -x IP_ADDRESS    ---reverse lookup of IP_ADDRESS
$ host domain          ---display DNS ip address for domain
$ hostname -i          ---display the network address of the host name.
$ hostname -I          ---display all local ip addresses
$ netstat -nutlp       ---display listening tcp and udp ports and corresponding programs
```
## ARCHIVES (TAR FILES)

```
$ tar cf  archive.tar directory      ---create tar named archive.tar containing directory.
$ tar xf  archive.tar                ---extract the contents from archive.tar.
$ tar czf archive.tar.gz directory   ---create a gzip compressed tar file name archive.tar.gz.
$ tar xzf archive.tar.gz             ---extract a gzip compressed tar file.
$ tar cjf archive.tar.bz2 directory  ---create a tar file with bzip2 compression
$ tar xjf archive.tar.bz2            ---extract a bzip2 compressed tar file.
```

## INSTALLING PACKAGES
 
```
$ yum search keyword    ---search for a package by keyword.
$ yum install package   ---install package.
$ yum info package      ---display description and summary information about package.
$ rpm -i package.rpm    ---install package from local file named package.rpm
$ yum remove package    ---remove/uninstall package.
$ tar zxvf sourcecode.tar.gz  ---install software from source code.
$ cd sourcecode
$ ./configure
$ make
$ make install
```

## SEARCH

```
$ grep pattern file                   ---search for pattern in file
$ grep -r pattern directory           ---search recursively for pattern in directory
$ locate name                         ---find files and directories by name
$ find /home/dir-name -name 'prefix*' ---find files in /home/dir-name that start with "prefix".
$ find /home -size +100M              ---find files larger than 100MB in /home
```

## SSH LOGINS

```
$ ssh host                ---connect to host as your local username.
$ ssh user@host           ---connect to host as user
$ ssh -p port user@host   ---connect to host using port
$ service ssh restart     
$ echo 'Some Text' | ssh user@host "cat > /remotefile.txt":
```

## FILE TRANSFERS

```
$ scp file.txt server:/tmp           ---secure copy file.txt to the /tmp folder on server
$ scp server:/var/www/*.html /tmp    ---copy *.html files from server to the local /tmp folder.
$ scp -r server:/var/www /tmp  
$ scp -r username@servername:/var/www/remotedir /var/www/localdir
$ scp -r localdir username@servername:remotedir
$ rsync -a /home /backups/           ---synchronize /home to /backups/home
$ rsync -avz /home server:/backups/  ---synchronize files/directories between the local and remote system with compression enabled
```

## DISK USAGE

```
$ df -h      ---show free and used space on mounted filesystems
$ df -i      ---show free and used inodes on mounted filesystems
$ fdisk -l   ---display disks partitions sizes and types
$ du -ah     ---display disk usage for all files and directories in human readable format
$ du -h --max-depth=1
$ du -sh     ---display total disk usage off the current directory
```

## DIRECTORY NAVIGATION

```
$ cd ..    ---change into the parent directory
$ cd       ---go to the $HOME directory
```

## SKILLS

```
$ sync; echo 1 > /proc/sys/vm/drop_caches   ---clear pagecache
$ sync; echo 2 > /proc/sys/vm/drop_caches   ---clear dentries and inodes
$ sync; echo 3 > /proc/sys/vm/drop_caches   ---clear pagecache, dentries and inodes
$ more /etc/passwd   ---list users
$ less /etc/passwd
$ awk -F':' '{ print $1}' /etc/passwd
$ awk -F":" '{print "Login:" $1 "\tName:" $5 "\tHome:" $6}' /etc/passwd
$ for i in {1..10};do echo $i;done          ---loop
$ while test "1"="1";do echo "test";done
$ while :;do echo "test";done
$ history | grep pattern                    ---search history
$ pstree -u                                 ---display the owner/user of a process
$ which name                                ---search program file
$ echo $?                                   ---last exit code
```