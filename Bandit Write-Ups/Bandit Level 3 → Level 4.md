## Level Goal
- The password for the next level is stored in a hidden file in the inhere directory.

## Performance
### Log in bandit 3
    ──(kali㉿Mono)-[~]
    └─$ ssh bandit3@bandit.labs.overthewire.org -p 2220
                             _                     _ _ _   
                            | |__   __ _ _ __   __| (_) |_ 
                            | '_ \ / _` | '_ \ / _` | | __|
                            | |_) | (_| | | | | (_| | | |_ 
                            |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                           
    
                          This is an OverTheWire game server. 
                More information on http://www.overthewire.org/wargames
    
    bandit3@bandit.labs.overthewire.org's password: 
    
    Permission denied, please try again.
    bandit3@bandit.labs.overthewire.org's password: 
    
    Permission denied, please try again.
    bandit3@bandit.labs.overthewire.org's password: 
    
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
    
    bandit3@bandit:~$ pwd
    /home/bandit3
    bandit3@bandit:~$ 
    
## Find the password for bandit4
    bandit3@bandit:~$ ls
    inhere
    bandit3@bandit:~$ cat inhere
    cat: inhere: Is a directory
    bandit3@bandit:~$ cd inhere
    bandit3@bandit:~/inhere$ ls
    bandit3@bandit:~/inhere$ ls -a
    .  ..  ...Hiding-From-You
    bandit3@bandit:~/inhere$ cat ...Hiding-From-You 
    2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
    bandit3@bandit:~/inhere$ 
