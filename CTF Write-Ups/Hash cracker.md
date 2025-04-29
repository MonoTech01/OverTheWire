## ne02 
- Connect to the network service at 3-ne04.bootupctf.net on port 8228 and retrieve the flag.

## Performance
Use netcat to connect to the server [nc domainname port]

    $ nc 3-ne04.bootupctf.net 8228
    Last session authenticated with: 5badcaf789d3d1d09794d8f021f40f0e
    Please verify your session. Password>

Retrieve the MD5 hash and enter it into an online cracking tool - such as [CrackStation](https://crackstation.net/) - to recover the original password

| Hash                                  | Type | Result   |
|---------------------------------------|:----:|:--------:|
| `5badcaf789d3d1d09794d8f021f40f0e`    | MD5  | starwars |

Find the flag

    $ nc 3-ne04.bootupctf.net 8228
    Last session authenticated with: 5badcaf789d3d1d09794d8f021f40f0e
    Please verify your session. Password> starwars
    User successfully authenticated.
    
    Flag: md5PReTTYoLdN0W679-88
