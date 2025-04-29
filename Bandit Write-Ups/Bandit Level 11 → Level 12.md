## Level Goal
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.

## Performance
### Log in bandit11
    ──(kali㉿Mono)-[~]
    └─$ ssh bandit11@bandit.labs.overthewire.org -p 2220
                             _                     _ _ _   
                            | |__   __ _ _ __   __| (_) |_ 
                            | '_ \ / _` | '_ \ / _` | | __|
                            | |_) | (_| | | | | (_| | | |_ 
                            |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                           
    
                          This is an OverTheWire game server. 
                More information on http://www.overthewire.org/wargames
    
    bandit11@bandit.labs.overthewire.org's password: 
### Find the password for bandit12
Look around and find out
    
    andit11@bandit:~$ ls
    data.txt
    bandit11@bandit:~$ cat data.txt 
    Gur cnffjbeq vf 7k16JArUVv5LxVuJfsSVdbbtaHGlw9D4
    
    bandit11@bandit:~$ tr --help
    Usage: tr [OPTION]... STRING1 [STRING2]
    Translate, squeeze, and/or delete characters from standard input,
    writing to standard output.  STRING1 and STRING2 specify arrays of
    characters ARRAY1 and ARRAY2 that control the action.
    ...
    [:lower:]       all lower case letters
    ...
    [:upper:]       all upper case letters
    ...
    
    bandit11@bandit:~$ cat data.txt | tr [a-z] [A-Z] 
    GUR CNFFJBEQ VF 7K16JARUVV5LXVUJFSSVDBBTAHGLW9D4
    
    bandit11@bandit:~$ cat data.txt | tr [a-z] [A-Z] | rot13
    Command 'rot13' not found, but can be installed with:
    apt install bsdgames  # version 2.17-30, or
    apt install hxtools   # version 20231101-1
    Ask your administrator to install one of them.
    
    bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
    The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4                               => the result


I just changed all the characters to uppercase for fun:

    bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m' | tr [a-z] [A-Z]
    THE PASSWORD IS 7X16WNEHII5YKIHWSFFIQOOGNUTYJ9Q4






    
