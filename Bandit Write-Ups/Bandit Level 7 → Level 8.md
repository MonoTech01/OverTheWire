## Level Goal
The password for the next level is stored in the file data.txt next to the word millionth
## Performance
### Log in bandit7
    ┌──(kali㉿Mono)-[~]
    └─$ ssh bandit7@bandit.labs.overthewire.org -p 2220
                             _                     _ _ _   
                            | |__   __ _ _ __   __| (_) |_ 
                            | '_ \ / _` | '_ \ / _` | | __|
                            | |_) | (_| | | | | (_| | | |_ 
                            |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                           
    
                          This is an OverTheWire game server. 
                More information on http://www.overthewire.org/wargames
    
    bandit7@bandit.labs.overthewire.org's password: 
    
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
### Find the password for bandit8

    bandit7@bandit:~$ ls
    data.txt
    bandit7@bandit:~$ cat data.txt 
    depression      q6X32st9sACqlScKXQlX2wbcvFecp9BP
    Claudette's     ykUWZY6KIy4bMKQild2792kmmU8GRXJV
    foretasting     oHqgsHvmgyVlDUouOx9FfhoLGJpUV23I
    dedication's    qSxXzVzrcCnpN5wuwvjWiS2rMom0xrx0
    dawns   mgdbA0BDN0O81gOhKgMPhGa1OVgQS75j
    ...
    kitchening      DXIVn1Qnd9qjlD5bISLRIHS4WnaYeMko
    reclining       6GyvNuAGX1HsImFYeA1O6ySrzBOdwFcb
    achoo   uZoJJJIm4xxaQTQKTTjpVH6q0goWRP6W
    detonators      0WF07wP9ZAnjSoS8OAP5tkgtZXPs6nZO
    steeple's       wYdpBlfQnvMCtt2BwVkPmUPkAlYUikvO

    bandit7@bandit:~$ cat data.txt | grep "millionth*"
    millionth       dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
