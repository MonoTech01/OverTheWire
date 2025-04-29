## SSH
    ssh karen@10.10.103.104

password: Password1
- Result:

      Last login: Thu Apr 24 17:01:46 2025 from ip-10-10-171-133.eu-west-1.compute.internal

## Enumeration
### 1. Hostname
    hostname
    (to get the hostname)
- Result:

      wade7363

### 2. Linux kernel version
    uname -a 
    (to retrieve system information, including the kernel version)

- Result:

      Linux wade7363 3.13.0-24-generic #46-Ubuntu SMP Thu Apr 10 19:11:08 UTC 2014 x86_64 x86_64 x86_64 GNU/Linux


### 3. Linux Version

1.

      cat /proc/version
      (to get details about the kernel and any installed compilers)

- Result:

      Linux version 3.13.0-24-generic (buildd@panlong) (gcc version 4.8.2 (Ubuntu 4.8.2-19ubuntu1) ) #46-Ubuntu SMP Thu Apr 10 19:11:08 UTC 2014

2.

      cat /etc/issue
      (to view the OS version information)

- Result:

      Ubuntu 14.04 LTS \n \l
    


### 4. Python

    python 
  - Result:

        Python 2.7.6 (default, Mar 22 2014, 22:59:56) 
        [GCC 4.8.2] on linux2
        Type "help", "copyright", "credits" or "license" for more information.
        >>>
### 5. Processes for the current shell

    ps
    (PID: The process ID (unique to the process)
    TTY: Terminal type used by the user
    Time: Amount of CPU time used by the process (this is NOT the time this process has been running for)
    CMD: The command or executable running (will NOT display any command line parameter))

    ps -A  (View all running processes)
    ps aux (Show processes for all users (a))
- Result:

          PID TTY          TIME CMD
         2300 pts/4    00:00:00 sh
         2401 pts/4    00:00:00 ps
### 6. Environmental variables

    en
    (The PATH variable may have a compiler or a scripting language (e.g. Python) that could be used to run code on the target system or leveraged for privilege escalation.)
- Result:

        MAIL=/var/mail/karen
        USER=karen
        SSH_CLIENT=10.10.171.133 55854 22
        HOME=/home/karen
        SSH_TTY=/dev/pts/4
        QT_QPA_PLATFORMTHEME=appmenu-qt5
        LOGNAME=karen
        TERM=xterm-256color
        XDG_SESSION_ID=3
        PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games
        XDG_RUNTIME_DIR=/run/user/1001
        LANG=en_US.UTF-8
        SHELL=/bin/sh
        PWD=/
        SSH_CONNECTION=10.10.171.133 55854 10.10.103.104 22

### 7. Discovering users on the system

    cat /etc/passwd
    (full)

    cat /etc/passwd | cut -d ":" -f 1
    (short and concise)

    cat /etc/passwd | grep home
    (real users will most likely have their folders under the “home” directory)

### 8. Networking <3

    ifconfig 
    (information about the network interfaces of the system)


    ip route
    (network routes)

    netstat -a
    (shows all listening ports and established connections)
    netstat -n
    (-n:  Do not resolve names)
    netstat -at or netstat -au 
    (lists TCP or UDP protocols respectively)
    netstat -l
    (lists ports in “listening” mode. These ports are open and ready to accept incoming connections. This can be used with the “t” option to list only ports that are listening using the TCP protocol such as netstat -lt)
    netstat -s 
    (lists network usage statistics by protocol.This can also be used with the -t or -u options to limit the output to a specific protocol.
    netstat -tp
    (lists connections with the service name and PID info)
    netstat -i
    (shows interface statistics) 
