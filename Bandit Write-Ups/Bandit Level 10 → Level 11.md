## Level Goal
The password for the next level is stored in the file data.txt, which contains base64 encoded data.

## Performance
###  Log in bandit10
    
    ┌──(kali㉿Mono)-[~]
    └─$ ssh bandit10@bandit.labs.overthewire.org -p 2220
                             _                     _ _ _   
                            | |__   __ _ _ __   __| (_) |_ 
                            | '_ \ / _` | '_ \ / _` | | __|
                            | |_) | (_| | | | | (_| | | |_ 
                            |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                           
    
                          This is an OverTheWire game server. 
                More information on http://www.overthewire.org/wargames
    
    bandit10@bandit.labs.overthewire.org's password: 
    ...
    bandit10@bandit:~$ 

### Find the password for bandit 11

Look around

    bandit10@bandit:~$ ls
    data.txt
    bandit10@bandit:~$ cat data.txt
    VGhlIHBhc3N3b3JkIGlzIGR0UjE3M2ZaS2IwUlJzREZTR3NnMlJXbnBOVmozcVJyCg==

The text was base64 encoded, so it's time to decode it to find the answer!
    
    bandit10@bandit:~$ cat data.txt | base64 -d
    The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr



