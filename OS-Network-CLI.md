# Linux CLI Cheatsheet for Network and OS commands

## <b>OS commands<b>

### [ps command](https://www.journaldev.com/24613/linux-ps-command)
It is used to get the information about the oricess running within your system.



#### The ps command without arguments lists the running processes in the current shell
```
ps
```
  
#### To have a glance at all the running processes, execute the command below
```
ps -A or ps -e
```
#### Command to display all process in current session
```
ps -T
```
#### To check process for a particular user
```
ps -u <username>
```
#### To check process run by a group
```
ps -fg <groupname>
```
#### To check all process with CPU and memory usage.
```
ps xu
```
#### To check process information of an application.
```
ps -C <application name>
```

### [top command](https://www.tecmint.com/12-top-command-examples-in-linux/)
The top command (table of processes) displays the processor activity of your Linux box and also displays tasks managed by the kernel in real-time. It also shows information about CPU and memory utilization of a list of running processes.


#### List all Running processes
```
top
```

All the below commands are run on top of 'top' command. First run 'top' command in cli and the use below commands.

#### Key to Change used memory value in human readable format. (Kb, Mb,Gb, Tb,Pb)
```
E
``` 

#### Key to check all core usage.
```
1
```

#### Key to check cpu usage in graphical format.
```
t
```

#### Key to check memory usage in graphical format.
```
m
```

#### Change color of top
```
z
```

#### to highlight top running memory process.
```
x
```

### to toggle between running app location to app.
```
c
```

#### To check process of a user
```
u
```

#### To kill a process
```
k
```

#### to quit top
```
q
```


### [df command](https://www.tecmint.com/how-to-check-disk-space-in-linux/)

df command is used to checkLinux disk space usage

#### Check file system disk usage
```
df
```

#### Display Information of all File System Disk Space Usage
```
df -a
```

#### Display Information of all File System Disk Space Usage in human readable format
```
df -ah
```

#### Type of disk with disk usage
```
df -T
```

#### To check a particular disk usage
```
df -T /<diskname> eg. disk -T /home
```

#### To check disk space in Kb.
```
df -k
```

#### To check disk space in Mb.
```
df -m
```

#### To check details of single types of disks.
```
df -t <disk format>  eg. df -t tmpfs/ext4
```


### [uname command](https://linuxize.com/post/uname-command-in-linux/)
uname is a command-line utility that prints basic information about the operating system name and system hardware.


#### Kernel name
```
uname
```

#### All information about system.
```
uname -a
```

#### Other arguments:
* -s, (--kernel-name) - Prints the kernel name.
* -n, (--nodename) - Prints the system’s node name (hostname). This is the name the system uses when communicating over the network. When used with the -n option, uname produces the same output as * the hostname command.
* -r, (--kernel-release) - Prints the kernel release.
* -v, (--kernel-version) - Prints the kernel version.
* -m, (--machine) - Prints the name of the machine’s hardware name.
* -p, (--processor) - Prints the architecture of the processor.
* -i, (--hardware-platform) - Prints the hardware platform.
* -o, (--operating-system) - Print the name of the operating system. On Linux systems that is “GNU/Linux”


### [free command](https://linuxize.com/post/free-command-in-linux/)
The free command provides information about the total amount of the physical and swap memory, as well as the free and used memory.

#### Check free memory
```
free
```

#### Check free memory in human readable format
```
free -h
```

#### Check free memory in Kb.
```
free -k
```

#### To show buffer and cache memory seperately.
```
free -wh
```

### [lspci](https://linuxhint.com/lspci_command/)
lspci command is a utility on linux systems used to find out information about the PCI busses and devices connected to the PCI subsystem.

#### All hardware component details
```
lspci
```

#### To get more information of hardware details
```
lspci -v
lspci -vv
lspci -vvv
```
#### Hardware details in script readable format.
```
lspci -m
```
#### To get kernel driver information for each hardware part.
```
lspci -k
```

### [kill command](https://linuxize.com/post/kill-command-in-linux/)
The kill command sends a signal to specified processes or process groups, causing them to act according to the signal. When the signal is not specified, it defaults to -15 (-TERM).

The most commonly used signals are:

* 1 (HUP) - Reload a process.
* 9 (KILL) - Kill a process.
* 15 (TERM) - Gracefully stop a process.

#### To get a list of all available signals, invoke the command with the -l option:
```
kill -l
```

#### The following commands are equivalent to one another:
```
kill -1 PID_NUMBER
kill -SIGHUP PID_NUMBER
kill -HUP PID_NUMBER
```

#### To kill a process like firefox:
```
kill -9 <Pid of firefox>
```

#### To reload a process
```
kill -1 <application Pid>
```
#### To gracefully stop a process.
```
kill <Pid of app> or kill -15 <pid of app>
```

### [ping command](https://linuxize.com/post/linux-ping-command/)
The ping command is one of the most used tools for troubleshooting, testing, and diagnosing network connectivity issues.

#### To continous check latency with any website like google
```
ping google.com
```

#### To send only n number of packets to any system. (eg. Below we are sending only one packet to google.com)
```
ping -c 1 google.com
```

#### Specify the Source Interface 
```
ping -I INTERFACE_NAME DESTINATION
```

#### To force ping to use IPv4, pass the -4 option, or use its alias ping4
```
ping -4 DESTINATION
```

#### For IPv6, pass the -6 option or use ping6
```
ping -6 DESTINATION
```

### [ifconfig](https://linuxize.com/post/ifconfig-command/)

ifconfig (interface configuration) is a network management tool. It is used to configure and view the status of the network interfaces in Linux operating systems.

#### Display Information of Network Interfaces #
```
ifconfig -a
```

#### To display the configuration information of any specific network interface
```
ifconfig wlo1/etho
```

#### to assign the IP address 192.168.0.101 and netmask 255.255.0.0 to the interface eth0
```
ifconfig eth0 192.168.0.101 netmask 255.255.0.0
```

#### Enable and Disable a Network Interface
```
ifconfig eth0/wlo1 down/up
```

### [SSH](https://linuxize.com/post/ssh-command-in-linux/)
Secure Shell (SSH) is a cryptographic network protocol used for an encrypted connection between a client and a server.

#### [SSH architecture](https://www.instagram.com/p/CVxyPnuL0WG/?utm_medium=copy_link)

#### To connect a server using ssh:
```
ssh <website>
```

#### To log in with different user:
```
ssh username@hostname or ssh -l username hostname
```

#### To log in with different user on a particular port (eg. 8022)
```
ssh username@hostname -p 8022
```











