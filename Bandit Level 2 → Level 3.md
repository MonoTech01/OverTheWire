## Level Goal
- The password for the next level is stored in a file called spaces in this filename located in the home directory.
## Performance
### Log in bandit2
    ┌──(kali㉿Mono)-[~]
    └─$ ssh bandit2@bandit.labs.overthewire.org -p 2220
                             _                     _ _ _   
                            | |__   __ _ _ __   __| (_) |_ 
                            | '_ \ / _` | '_ \ / _` | | __|
                            | |_) | (_| | | | | (_| | | |_ 
                            |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                           
    
                          This is an OverTheWire game server. 
                More information on http://www.overthewire.org/wargames
    
    bandit2@bandit.labs.overthewire.org's password: 
    
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
    
    bandit2@bandit:~$ 
### Find the password for bandit3
    bandit2@bandit:~$ pwd
    /home/bandit2
    bandit2@bandit:~$ ls -a
    .  ..  .bash_logout  .bashrc  .profile  spaces in this filename
    bandit2@bandit:~$ cat spaces
    cat: spaces: No such file or directory
    bandit2@bandit:~$ cat spaces\ in\ this\ filename 
    MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
    bandit2@bandit:~$ 


