## Level Goal
- The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

    human-readable
  
    1033 bytes in size

    not executable
## Performance
### Log in bandit 5
    ┌──(kali㉿Mono)-[~]
    └─$ ssh bandit5@bandit.labs.overthewire.org -p 2220
                             _                     _ _ _   
                            | |__   __ _ _ __   __| (_) |_ 
                            | '_ \ / _` | '_ \ / _` | | __|
                            | |_) | (_| | | | | (_| | | |_ 
                            |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                           
    
                          This is an OverTheWire game server. 
                More information on http://www.overthewire.org/wargames
    
    bandit5@bandit.labs.overthewire.org's password: 
    
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
    
    ...
    
    bandit5@bandit:~$ 
    
### Find the password for bandit 6
    bandit5@bandit:~/inhere$ find . -type f -size 1033c ! -executable
    ./maybehere07/.file2
    bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
    HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

