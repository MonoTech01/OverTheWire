## Level Goal
- The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.
## Performance
### Log in bandit9
    ┌──(kali㉿Mono)-[~]
    └─$ ssh bandit9@bandit.labs.overthewire.org -p 2220
                             _                     _ _ _   
                            | |__   __ _ _ __   __| (_) |_ 
                            | '_ \ / _` | '_ \ / _` | | __|
                            | |_) | (_| | | | | (_| | | |_ 
                            |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                           
    
                          This is an OverTheWire game server. 
                More information on http://www.overthewire.org/wargames
    
    bandit9@bandit.labs.overthewire.org's password: 
    
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

### Find the password for bandit10

Look around and find out

    9@bandit:~$ ls                                                               
    data.txt
    bandit9@bandit:~$ cat data.txt
    ��4aSSW�ҭ��j�s�E���K4���,��l0@P(��gw�)����2�l�BJ�
    ����,k=?��|Y������@����-�-t=�]�bڊ�˯���N8�k��zR|?K�(Vbj�6F)��Wg&�<u�5� ^�k���r��������
            tIsrQzk`Dl5�ʖ<f'��/%�!%P�0��]�]��jH
    &�x�YV;���0�k�^GV�B���X7;96�t���
    ...
    �▒���t��g���~����ڼ?as�cl�g�K#��F��$*�;��#��V��*��Z;�u��v*��▒�e}��v�c
    U6���o�x�V]�!�Xq�є��S�y��������m
    c�"��l>IF<¨"��ʋM���GHof/;��▒)
    ��8".�x�5Q���_Fo�b`��d���/��^8m�7���]
    ���{�uG_V����fJ<�ʐ|e�B�Z(+���&X����F՚���T�@Ǿ=˚I��3s��8���js3v�^t��
    �D�▒��*�U��>���ZaW����N�O6���▒=#�}�x▒����8L�{�4k���R�6�v!x�F"��֏�,~襪pY
    
    
    bandit9@bandit:~$ file data.txt 
    data.txt: data
    
    bandit9@bandit:~$ strings data.txt
    l0@P(
    ,k=?
    tIsrQ
    ...
    Tvw1
    Ns9(
    //'av
    ========== the
    2xG&
    O;O1
    ...
    qC^4
    y})
    H7*E
    ========== password{k
    ]AOJ
    ...
    4u|@{F*
    OS      4
    ;`[;z
    =========== is
    {~j@e
    *dx%A
    ...
    bD/@
    2wNXK|
    ========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
    v3A|
    ...
    uG_V

    bandit9@bandit:~$ strings data.txt | grep "=*" -o
    =
    =
    ==========
    =
    =
    =
    =
    ==========
    ===========
    =
    =
    =
    =
    =
    ==========
    =
    =
    bandit9@bandit:~$ 

I found 4 lines with long =, and they have at least ========== amount of =. Therefore, I used the length for my search below

    bandit9@bandit:~$ strings data.txt | grep "==========" -n
    18:========== the
    67:========== password{k
    83:=========== is
    188:========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey







