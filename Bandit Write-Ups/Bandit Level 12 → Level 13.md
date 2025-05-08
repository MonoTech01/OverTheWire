## Level Goal
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed.

## Performance
### Log in bandit12

    ┌──(kali㉿Mono)-[~]
    └─$ ssh bandit12@bandit.labs.overthewire.org -p 2220
                             _                     _ _ _   
                            | |__   __ _ _ __   __| (_) |_ 
                            | '_ \ / _` | '_ \ / _` | | __|
                            | |_) | (_| | | | | (_| | | |_ 
                            |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                           
    
                          This is an OverTheWire game server. 
                More information on http://www.overthewire.org/wargames
    
    bandit12@bandit.labs.overthewire.org's password: 

### Find the password for bandit13

Look around and find out

    bandit12@bandit:~$ ls
    data.txt
    
    bandit12@bandit:~$ cat data.txt 
    00000000: 1f8b 0808 41d4 f767 0203 6461 7461 322e  ....A..g..data2.
    00000010: 6269 6e00 0149 02b6 fd42 5a68 3931 4159  bin..I...BZh91AY
    00000020: 2653 59a8 ffa7 8f00 001d 7fff dbeb 7ffa  &SY.............
    00000030: bb7f a5ef bb7e f5fb fdff b7c7 f3ff ff7f  .....~..........
    00000040: ff7f fff7 deba fdfa eff7 dddf b001 3b19  ..............;.
    00000050: a200 d01a 0190 0034 0006 800d 0340 0346  .......4.....@.F
    00000060: 8000 0340 0320 0069 a034 0640 0346 4680  ...@. .i.4.@.FF.
    00000070: 68d1 a68c 8321 9313 4da4 f510 6406 8003  h....!..M...d...
    00000080: 4006 9a00 000d 000d 0069 a007 a9a0 001a  @........i......
    00000090: 1b50 03d4 01a6 9a1e a001 a343 4683 469a  .P.........CF.F.
    000000a0: 3d40 001a 7a8d 01a0 074c 801e a1a6 8064  =@..z....L.....d
    000000b0: 01a3 d434 00c4 0d00 000d 0001 a680 1a19  ...4............
    000000c0: 0061 0f53 41a0 0000 0d00 341a 0320 0034  .a.SA.....4.. .4
    000000d0: d1ea 0168 4882 8244 0130 5550 f16b f52e  ...hH..D.0UP.k..
    000000e0: a322 cb9f bb8c aaf6 e244 cc70 b151 47c8  .".......D.p.QG.
    000000f0: 6c03 a3ae 4a81 1ee0 03ce 840e a978 2046  l...J........x F
    00000100: 630b 4b0d 9883 7078 e7e8 5bfb 68f1 f685  c.K...px..[.h...
    00000110: 6f46 771c 3920 449f f0cb 39e2 0841 10b5  oFw.9 D...9..A..
    00000120: 8714 e981 115c d1bc 2da4 318b 106c 904e  .....\..-.1..l.N
    00000130: 9328 5e97 405a 4054 21db e049 1a32 5f3d  .(^.@Z@T!..I.2_=
    00000140: 7069 408f f0a4 8ce5 fbea 282c 51d1 49e4  pi@.......(,Q.I.
    00000150: d52f 0762 dd90 27b8 79d3 0499 52e0 060c  ./.b..'.y...R...
    00000160: fd91 a474 d408 88f3 1fda d2d1 325a baeb  ...t........2Z..
    00000170: bfe7 f0f6 cc3c 776d f369 e73c 47d4 66ea  .....<wm.i.<G.f.
    00000180: 4b90 e404 03b3 6a09 4687 945d 09ef 706b  K.....j.F..]..pk
    00000190: 8f82 2503 80d0 0a0a 3e60 f879 bf02 2d42  ..%.....>`.y..-B
    000001a0: bf37 9c96 4b22 585c 35c8 3cf1 da9f 518b  .7..K"X\5.<...Q.
    000001b0: ccd5 a68c 9647 aa38 8a50 89d2 f89c 1ff0  .....G.8.P......
    000001c0: 1042 18c3 6549 400d fe17 ec74 3171 6d74  .B..eI@....t1qmt
    000001d0: a8bb 0def f11a 5a69 0e70 aa34 0037 b180  ......Zi.p.4.7..
    000001e0: 1540 c4d2 0af7 e290 8784 ce9e 147a 6836  .@...........zh6
    000001f0: 944b 3f18 2ba2 c620 af92 fb01 184f 3def  .K?.+.. .....O=.
    00000200: 1b7d 0162 733d adca 90ac 7142 8319 f703  .}.bs=....qB....
    00000210: 5930 69e2 8320 9110 5d63 0db9 9294 d4ef  Y0i.. ..]c......
    00000220: 50b9 5907 0924 92c1 014e a284 25ce a6ef  P.Y..$...N..%...
    00000230: 67b2 4e06 6d21 4136 2ac0 292d 6638 033c  g.N.m!A6*.)-f8.<
    00000240: 21af be4e 13bb b74f 2c10 18c7 eea3 c436  !..N...O,......6
    00000250: c988 05e6 5638 1ff1 7724 5385 090a 8ffa  ....V8..w$S.....
    00000260: 78f0 d951 192d 4902 0000                 x..Q.-I...
    bandit12@bandit:~$ 

### Find the password for bandit13

    bandit12@bandit:~$ mkdir /tmp/monoworkshop
    bandit12@bandit:~$ cd /tmp/monoworkshop
    bandit12@bandit:/tmp/monoworkshop$ cp ~/data.txt 
    cp: missing destination file operand after '/home/bandit12/data.txt'
    Try 'cp --help' for more information.
    bandit12@bandit:/tmp/monoworkshop$ cp ~/data.txt .
    bandit12@bandit:/tmp/monoworkshop$ ls
    data.txt
    bandit12@bandit:/tmp/monoworkshop$ 

Convert the hex data back into raw binary
    
    bandit12@bandit:/tmp/monoworkshop$ xxd -r data.txt 
    4▒ 4��hH��D0UP�k�.�"˟�����D�p�QG�l��J��΄�x Fc������޺�����;��▒�4�
    ��px��[�h���oFw9 D���9A����\Ѽ-�1�l�N�(^�@Z@T!��I▒2_=pi@�������(,Q�I��/bݐ'�y��R�
      ���t�����2Z�������<wm�i�<G�f�K���j    F��]    �pk��%��
    
    ��▒Zip�47��@��\5�<�ڟQ��զ��G�8�P�����B▒�eI@
    �����P�YK?▒+�� �$��N��%Φ�g�Nm!A6*�)-f8<!��N��O,▒����6Ɉ�V8�w$S�
    ��x��Q-Ibandit12@bandit:/tmp/monoworkshop$ 

    bandit12@bandit:/tmp/monoworkshop$ xxd -r data.txt > binary
    bandit12@bandit:/tmp/monoworkshop$ ls
    binary  data.txt

    bandit12@bandit:/tmp/monoworkshop$ file ./*
    ./binary:   gzip compressed data, was "data2.bin", last modified: Thu Apr 10 14:22:57 2025, max compression, from Unix, original size modulo 2^32       585
    ./data.txt: ASCII text

Decompress .gz
    bandit12@bandit:/tmp/monoworkshop$ mv binary file.gz
    bandit12@bandit:/tmp/monoworkshop$ gunzip file.gz 
    bandit12@bandit:/tmp/monoworkshop$ ls
    data.txt  file
    bandit12@bandit:/tmp/monoworkshop$ file file
    file: bzip2 compressed data, block size = 900k
    
Decompress .bz    
    bandit12@bandit:/tmp/monoworkshop$ mv file file.bz
    bandit12@bandit:/tmp/monoworkshop$ bzip -d file.bz
    Command 'bzip' not found, but there are 21 similar ones.
    bandit12@bandit:/tmp/monoworkshop$ bzip2 -d file.bz
    bandit12@bandit:/tmp/monoworkshop$ ls
    data.txt  file
    bandit12@bandit:/tmp/monoworkshop$ file file
    file: gzip compressed data, was "data4.bin", last modified: Thu Apr 10 14:22:57 2025, max compression, from Unix, original size modulo 2^32 20480

Decompress .gz
    bandit12@bandit:/tmp/monoworkshop$ mv file file.gz
    bandit12@bandit:/tmp/monoworkshop$ gunzip file.gz 
    bandit12@bandit:/tmp/monoworkshop$ ls
    data.txt  file
    bandit12@bandit:/tmp/monoworkshop$ file *
    data.txt:   ASCII text
    file:       POSIX tar archive (GNU)
        
Rename .tar and extract
    bandit12@bandit:/tmp/monoworkshop$ mv file file.tar
    bandit12@bandit:/tmp/monoworkshop$ tar -xf file.tar 
    bandit12@bandit:/tmp/monoworkshop$ ls
    data5.bin  data.txt  file.tar

 Rename .tar and extract      
    bandit12@bandit:/tmp/monoworkshop$ mv data5.bin data.tar
    bandit12@bandit:/tmp/monoworkshop$ tar -xf data.tar 
    bandit12@bandit:/tmp/monoworkshop$ ls
    data6.bin  data.tar  data.txt  file.tar

 Rename .tar and extract
    bandit12@bandit:/tmp/monoworkshop$ mv data6.bin data.tar
    bandit12@bandit:/tmp/monoworkshop$ tar -xf data.tar 
    bandit12@bandit:/tmp/monoworkshop$ ls
    data8.bin  data.tar  data.txt  file.tar

Rename .tar and extract        
    bandit12@bandit:/tmp/monoworkshop$ mv data8.bin data.tar
    bandit12@bandit:/tmp/monoworkshop$ ls
    data.tar  data.txt  file.tar
    bandit12@bandit:/tmp/monoworkshop$ tar -xf data.tar 
    bandit12@bandit:/tmp/monoworkshop$ ls
    data.tar  data.txt  file.tar
    bandit12@bandit:/tmp/monoworkshop$ file *
    data.tar:   gzip compressed data, was "data9.bin", last modified: Thu Apr 10 14:22:57 2025, max compression, from Unix, original size modulo 2^32 49
    data.txt:   ASCII text
    file.tar:   POSIX tar archive (GNU)

Decompress .gz
    bandit12@bandit:/tmp/monoworkshop$ mv data.tar data.gz
    bandit12@bandit:/tmp/monoworkshop$ gzip -d data.gz
    bandit12@bandit:/tmp/monoworkshop$ ls
    data  data.txt  file.tar
    bandit12@bandit:/tmp/monoworkshop$ file *
    data:       ASCII text
    data.txt:   ASCII text
    file.tar:   POSIX tar archive (GNU)
        
The final data file is ASCII text and readable!  
    bandit12@bandit:/tmp/monoworkshop$ cat data
    The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn                     => The result!!!
    bandit12@bandit:/tmp/monoworkshop$ 
           
        
        
