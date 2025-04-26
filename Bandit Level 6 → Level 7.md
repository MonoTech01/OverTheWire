## Level Goal
The password for the next level is stored somewhere on the server and has all of the following properties:
- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

## Performance
### Log in bandit6

    ┌──(kali㉿Mono)-[~]
    └─$ ssh bandit6@bandit.labs.overthewire.org -p 2220
                             _                     _ _ _   
                            | |__   __ _ _ __   __| (_) |_ 
                            | '_ \ / _` | '_ \ / _` | | __|
                            | |_) | (_| | | | | (_| | | |_ 
                            |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                           
    
                          This is an OverTheWire game server. 
                More information on http://www.overthewire.org/wargames
    
    bandit6@bandit.labs.overthewire.org's password: 
    
          ,----..            ,----,          .---.
         /   /   \         ,/   .`|         /. ./|
        /   .     :      ,`   .'  :     .--'.  ' ;
       .   /   ;.  \   ;    ;     /    /__./ \ : |
      .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
      ;   |  ; \ ; | |    :     | /___/ \ |    ' '
      |   :  | ; | ' ;    |.';  ; ;   \  \;      :
      .   |  ' ' ' : `----'  |  |  \   ;  `      |
      '   ;  \; /  |     '   :  ;   .   \    .\  ;
       \   \  ',  /      |   |  '    \   \   ' \ |
        ;   :    /       '   :  |     :   '  |--"
         \   \ .'        ;   |.'       \   \ ;
      www. `---` ver     '---' he       '---" ire.org
    
    
    Welcome to OverTheWire!

### Find the password for bandit 7

Look around

    bandit6@bandit:~$ ls
    bandit6@bandit:~$ ls -a
    .  ..  .bash_logout  .bashrc  .profile
    
    bandit6@bandit:~$ file ./.*
    ./.bash_logout: ASCII text
    ./.bashrc:      ASCII text
    ./.profile:     ASCII text

I used "cat" to read the files and found out nothing was important in there!

Locate the password by using the provided info

    bandit6@bandit:~$ find / -user bandit7 -size 33c -group bandit6
    find: ‘/root’: Permission denied
    find: ‘/proc/tty/driver’: Permission denied
    find: ‘/proc/623770/task/623770/fd/6’: No such file or directory
    ...
    find: ‘/var/lib/udisks2’: Permission denied
    find: ‘/var/lib/update-notifier/package-data-downloads/partial’: Permission denied
    find: ‘/var/lib/polkit-1’: Permission denied
    /var/lib/dpkg/info/bandit7.password
    find: ‘/var/lib/apt/lists/partial’: Permission denied
    ...
    find: ‘/tmp’: Permission denied

    bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
    morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj




