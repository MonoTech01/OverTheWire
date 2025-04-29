## Level Goal
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once
## Performance
### Log in bandit8
    ┌──(kali㉿Mono)-[~]
    └─$ ssh bandit8@bandit.labs.overthewire.org -p 2220
                             _                     _ _ _   
                            | |__   __ _ _ __   __| (_) |_ 
                            | '_ \ / _` | '_ \ / _` | | __|
                            | |_) | (_| | | | | (_| | | |_ 
                            |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                           
    
                          This is an OverTheWire game server. 
                More information on http://www.overthewire.org/wargames
    
    bandit8@bandit.labs.overthewire.org's password: 
    
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

### Find the password for bandit9
Locate the data.txt file

    bandit8@bandit:~$ ls -a
    .  ..  .bash_logout  .bashrc  data.txt  .profile
    
Check options for uniq command 
    
    bandit8@bandit:~$ man uniq
    ...
     -u, --unique only print unique lines
    ...
    [1]+  Stopped                 man uniq

Find the password for bandit9
    
    bandit8@bandit:~$ sort data.txt | uniq -u
    4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
    
