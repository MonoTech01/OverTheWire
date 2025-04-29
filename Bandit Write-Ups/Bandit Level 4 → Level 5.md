## Level Goal
- The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

## Performance
### Log in badit4
    ┌──(kali㉿Mono)-[~]
    └─$ ssh bandit4@bandit.labs.overthewire.org -p 2220
                             _                     _ _ _   
                            | |__   __ _ _ __   __| (_) |_ 
                            | '_ \ / _` | '_ \ / _` | | __|
                            | |_) | (_| | | | | (_| | | |_ 
                            |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                           
    
                          This is an OverTheWire game server. 
                More information on http://www.overthewire.org/wargames
    
    bandit4@bandit.labs.overthewire.org's password: 
    
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
    
    bandit4@bandit:~$ 




### Find the password for bandit5

    bandit4@bandit:~/inhere$ ls -a
    .   -file00  -file02  -file04  -file06  -file08
    ..  -file01  -file03  -file05  -file07  -file09
    
    bandit4@bandit:~/inhere$ more -file00
    more: invalid option -- 'i'
    Try 'more --help' for more information.
    bandit4@bandit:~/inhere$ more ./-file00
    �ŉOT���S �plS]-EH�t�:-�Z�^L
    
    bandit4@bandit:~/inhere$ file./-*
    -bash: file./-*: No such file or directory
    bandit4@bandit:~/inhere$ file ./-*
    ./-file00: PGP Secret Sub-key -
    ./-file01: data
    ./-file02: data
    ./-file03: data
    ./-file04: data
    ./-file05: data
    ./-file06: data
    ./-file07: ASCII text
    ./-file08: data
    ./-file09: data
    
    bandit4@bandit:~/inhere$ cat ./-file07
    4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
    bandit4@bandit:~/inhere$ 
