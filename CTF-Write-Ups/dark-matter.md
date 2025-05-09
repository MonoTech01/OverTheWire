## Target Info & Mission
- DarkInjector’s ransomware has encrypted Hackfinity High School’s files but left debugging output in /tmp.
- Connect to the VM and find RSA private key => Find the flag.
- There is a ransomeware note on the screen:

      Ransomware Note
      
      You have been pwned by the DarkMatter  Gang.
      Your files have been encrypted!
      
      71:50:13
      
      Enter the decryption key:
      [              ]
      
      Decrypt
      
      Pay 0.5 BTC to: 1A2B3C4D5E6F7G8H9I0J1K2L3M4N5O6P7Q8R9S0T1U2V3W4X5Y6Z7
      Failure to comply will result in permanent data loss.



## Performance

Go to the machine and examine /tmp

    ubuntu@tryhackme:~$ cd /tmp
    ubuntu@tryhackme:/tmp$ ls
    dock-replace.log
    encrypted_aes_key.bin
    public_key.txt

Read the public key file

    ubuntu@tryhackme:/tmp$ cat public_key.txt
    n=340282366920938460843936948965011886881
    e=65537
    ubuntu@tryhackme:/tmp$

The content of public key file reveals 2 important factors of creating RSA key (n and e). In the RSA key formular, the pair (n, e) is the public key, and the pair (n,d) is the private key. Thanks to the infomation of the public key, finding the decryption is easier now.

Go to this RSA decoder tool https://www.dcode.fr/rsa-cipher and fill in these following info:

    Pubic key E = 65537
    
    Public key value = 340282366920938460843936948965011886881

The result of the decoder show many possible decryption (d) keys. After putting each key in "Enter the decryption key" section, the following key is the correct one: 19644236187324098433228745541797845217


The correct key unlocks the machine and allows users to access the school's files. 

I went through each files and found the flag in "Student Grades Report" file.



