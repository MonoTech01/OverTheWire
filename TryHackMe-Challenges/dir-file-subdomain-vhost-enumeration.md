## Target Info & Mission
- Task 1: Enumerate the directories of `www.offensivetools.thm` Which directory catches your attention?
- Task 2: Continue enumerating the directory found in task 1. What is the flag found in this file?
- Task 3: How many subdomains are configured for the offensivetools.thm domain?
- Task 4: How many vhosts on the offensivetools.thm domain reply with a status code 200?

## Performance
### Task 1
    root@ip-10-10-84-71:~# gobuster dir -u "www.offensivetools.thm" -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
    ===============================================================
    Gobuster v3.6
    by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
    ===============================================================
    [+] Url:                     http://www.offensivetools.thm
    [+] Method:                  GET
    [+] Threads:                 10
    [+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
    [+] Negative Status codes:   404
    [+] User Agent:              gobuster/3.6
    [+] Timeout:                 10s
    ===============================================================
    Starting gobuster in directory enumeration mode
    ===============================================================
    /images               (Status: 301) [Size: 333] [--> http://www.offensivetools.thm/images/]
    /home                 (Status: 200) [Size: 8818]
    /media                (Status: 301) [Size: 332] [--> http://www.offensivetools.thm/media/]
    /templates            (Status: 301) [Size: 336] [--> http://www.offensivetools.thm/templates/]
    /modules              (Status: 301) [Size: 334] [--> http://www.offensivetools.thm/modules/]
    /plugins              (Status: 301) [Size: 334] [--> http://www.offensivetools.thm/plugins/]
    /includes             (Status: 301) [Size: 335] [--> http://www.offensivetools.thm/includes/]
    /language             (Status: 301) [Size: 335] [--> http://www.offensivetools.thm/language/]
    /components           (Status: 301) [Size: 337] [--> http://www.offensivetools.thm/components/]
    /api                  (Status: 301) [Size: 330] [--> http://www.offensivetools.thm/api/]
    /cache                (Status: 301) [Size: 332] [--> http://www.offensivetools.thm/cache/]
    /libraries            (Status: 403) [Size: 287]
    /tmp                  (Status: 301) [Size: 330] [--> http://www.offensivetools.thm/tmp/]
    /layouts              (Status: 301) [Size: 334] [--> http://www.offensivetools.thm/layouts/]
    /secret               (Status: 301) [Size: 333] [--> http://www.offensivetools.thm/secret/]
    /administrator        (Status: 301) [Size: 340] [--> http://www.offensivetools.thm/administrator/]
    Progress: 6501 / 218276 (2.98%)^Z
    [1]+  Stopped                 gobuster dir -u "www.offensivetools.thm" -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt

/secret catches my attention!

### Task 2

    root@ip-10-10-84-71:~# gobuster dir -u "www.offensivetools.thm/secret" -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x .js
    ===============================================================
    Gobuster v3.6
    by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
    ===============================================================
    [+] Url:                     http://www.offensivetools.thm/secret
    [+] Method:                  GET
    [+] Threads:                 10
    [+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
    [+] Negative Status codes:   404
    [+] User Agent:              gobuster/3.6
    [+] Extensions:              js
    [+] Timeout:                 10s
    ===============================================================
    Starting gobuster in directory enumeration mode
    ===============================================================
    /content              (Status: 301) [Size: 341] [--> http://www.offensivetools.thm/secret/content/]
    /uploads              (Status: 301) [Size: 341] [--> http://www.offensivetools.thm/secret/uploads/]
    /flag.js              (Status: 200) [Size: 22]
    Progress: 3593 / 436552 (0.82%)^Z
    [3]+  Stopped                 gobuster dir -u "www.offensivetools.thm/secret" -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x .js

The interesting found file is flag.js

Go to `www.offensivetools.thm/secret/flag.js` and find the flag is THM{ReconWasASuccess}

### Task 3

    root@ip-10-10-84-71:~# gobuster dns -d offensivetools.thm -w /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt
    ===============================================================
    Gobuster v3.6
    by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
    ===============================================================
    [+] Domain:     offensivetools.thm
    [+] Threads:    10
    [+] Timeout:    1s
    [+] Wordlist:   /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt
    ===============================================================
    Starting gobuster in DNS enumeration mode
    ===============================================================
    Found: www.offensivetools.thm
    
    Found: forum.offensivetools.thm
    
    Found: store.offensivetools.thm
    
    Found: WWW.offensivetools.thm
    
    Found: primary.offensivetools.thm
    
    Progress: 4997 / 4998 (99.98%)
    ===============================================================
    Finished
    ===============================================================


4 subdomains

### Task 4

    root@ip-10-10-84-71:~# gobuster vhost -u "http://10.10.125.12" --domain example.thm -w /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt --append-domain --exclude-length 250-320 
    ===============================================================
    Gobuster v3.6
    by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
    ===============================================================
    [+] Url:              http://10.10.125.12
    [+] Method:           GET
    [+] Threads:          10
    [+] Wordlist:         /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt
    [+] User Agent:       gobuster/3.6
    [+] Timeout:          10s
    [+] Append Domain:    true
    [+] Exclude Length:   264,277,291,306,313,315,267,268,294,297,309,253,251,252,269,272,282,290,301,312,316,266,288,289,293,295,296,304,317,273,298,318,257,311,320,256,286,250,275,300,319,265,276,278,279,281,260,271,274,307,310,259,263,270,284,287,299,303,308,314,255,261,262,283,292,302,254,258,280,285,305
    ===============================================================
    Starting gobuster in VHOST enumeration mode
    ===============================================================
    Found: blog.example.thm Status: 200 [Size: 1493]
    Found: shop.example.thm Status: 200 [Size: 2983]
    Found: academy.example.thm Status: 200 [Size: 434]
    Found: www.example.thm Status: 200 [Size: 84352]
    Progress: 4997 / 4998 (99.98%)
    Found: WWW.example.thm Status: 200 [Size: 84352]
    ===============================================================
    Finished
    ===============================================================
    root@ip-10-10-84-71:~# 

3 Vhosts




