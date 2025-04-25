## Level Goal
- The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

## Performance
### Find password
    bandit0@bandit:~$ ls
    readme
    bandit0@bandit:~$ cat readme
    Congratulations on your first steps into the bandit game!!
    Please make sure you have read the rules at https://overthewire.org/rules/
    If you are following a course, workshop, walkthrough or other educational activity,
    please inform the instructor about the rules as well and encourage them to
    contribute to the OverTheWire community so we can keep these games free!
    
    The password you are looking for is: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
    
    bandit0@bandit:~$ 

### Log in with bandit1 account
        ┌──(kali㉿Mono)-[~]
        └─$ ssh bandit1@bandit.labs.overthewire.org -p 2220
                                 _                     _ _ _   
                                | |__   __ _ _ __   __| (_) |_ 
                                | '_ \ / _` | '_ \ / _` | | __|
                                | |_) | (_| | | | | (_| | | |_ 
                                |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                               
        
                              This is an OverTheWire game server. 
                    More information on http://www.overthewire.org/wargames
        
        bandit1@bandit.labs.overthewire.org's password: 
        
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
        
        bandit1@bandit:~$

