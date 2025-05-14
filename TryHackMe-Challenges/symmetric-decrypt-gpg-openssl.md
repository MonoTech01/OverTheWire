## Target Info & Mission

Task 1. **Decrypt `quote01`**  
   - **Tool:** GPG  
   - **Cipher:** AES256  
   - **Key:** `s!kR3T55`  
   - **Question:** What is the third word in the decrypted file?

Task 2. **Decrypt `quote02`**  
   - **Tool:** OpenSSL  
   - **Cipher:** AES-256-CBC  
   - **Key:** `s!kR3T55`  
   - **Question:** What is the third word in the decrypted file?

Task 3. **Decrypt `quote03`**  
   - **Tool:** GPG  
   - **Cipher:** CAMELLIA256  
   - **Key:** `s!kR3T55`  
   - **Question:** What is the third word in the decrypted file?

## Performance
Locate the files

    root@ip-10-10-255-38:~/Rooms/cryptographyintro/task02# ls
    quote01.txt.gpg  quote02  quote03.txt.gpg
    
### Task 1 

    root@ip-10-10-255-38:~/Rooms/cryptographyintro/task02# gpg -o quote01.txt -d quote01.txt.gpg

            x Enter passphrase                                     x            
            x                                                      x            
            x                                                      x            
            x Passphrase: ________________________________________ x            
            x                                                      x            
            x       <OK>                              <Cancel>     x  
    
    gpg: AES256 encrypted data
    gpg: encrypted with 1 passphrase
    root@ip-10-10-255-38:~/Rooms/cryptographyintro/task02# ls
    quote01.txt  quote01.txt.gpg  quote02  quote03.txt.gpg
    root@ip-10-10-255-38:~/Rooms/cryptographyintro/task02# cat quote01.txt
    Do not waste time idling or thinking after you have set your goals.
    Miyamoto Musashi

The third word in the decrypted file is "waste".

### Task 2
Note: Use the openssl help command to display the correct cipher format syntax.

    root@ip-10-10-255-38:~/Rooms/cryptographyintro/task02# openssl aes-256-cbc -d -in quote02 -out quote02.txt
    enter aes-256-cbc decryption password:
    *** WARNING : deprecated key derivation used.
    Using -iter or -pbkdf2 would be better.
    root@ip-10-10-255-38:~/Rooms/cryptographyintro/task02# ls
    quote01.txt      quote02       quote02.txt  quote03.txt.gpg
    quote01.txt.gpg  quote022.txt  quote03.txt
    root@ip-10-10-255-38:~/Rooms/cryptographyintro/task02# cat quote02.txt
    The true science of martial arts means practicing them in such a way that they will be useful at any time, and to teach them in such a way that they will be useful in all things.
    Miyamoto Musashi

The third word in the decrypted file is "science".

### Task 3

    root@ip-10-10-255-38:~/Rooms/cryptographyintro/task02# gpg -o quote03.txt -d quote03.txt.gpg
    gpg: CAMELLIA256 encrypted data
    gpg: encrypted with 1 passphrase
    gpg: decryption failed: Bad session key
    root@ip-10-10-255-38:~/Rooms/cryptographyintro/task02# gpg -o quote03.txt -d quote03.txt.gpg
    gpg: CAMELLIA256 encrypted data
    gpg: encrypted with 1 passphrase
    root@ip-10-10-255-38:~/Rooms/cryptographyintro/task02# ls
    quote01.txt  quote01.txt.gpg  quote02  quote03.txt  quote03.txt.gpg
    root@ip-10-10-255-38:~/Rooms/cryptographyintro/task02# cat quote03.txt
    You must understand that there is more than one path to the top of the mountain.
    Miyamoto Musashi

The third word in the decrypted file is "understand".
