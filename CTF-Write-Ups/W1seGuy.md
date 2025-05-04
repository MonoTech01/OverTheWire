## Target's info

- IP address: 10.10.213.102
- The server is listening on port 1337 via TCP
- Source code:

      import random
      import socketserver 
      import socket, os
      import string
      
      flag = open('flag.txt','r').read().strip()
      
      def send_message(server, message):
          enc = message.encode()
          server.send(enc)
      
      def setup(server, key):
          flag = 'THM{thisisafakeflag}' 
          xored = ""
      
          for i in range(0,len(flag)):
              xored += chr(ord(flag[i]) ^ ord(key[i%len(key)]))
      
          hex_encoded = xored.encode().hex()
          return hex_encoded
      
      def start(server):
          res = ''.join(random.choices(string.ascii_letters + string.digits, k=5))
          key = str(res)
          hex_encoded = setup(server, key)
          send_message(server, "This XOR encoded text has flag 1: " + hex_encoded + "\n")
          
          send_message(server,"What is the encryption key? ")
          key_answer = server.recv(4096).decode().strip()
      
          try:
              if key_answer == key:
                  send_message(server, "Congrats! That is the correct key! Here is flag 2: " + flag + "\n")
                  server.close()
              else:
                  send_message(server, 'Close but no cigar' + "\n")
                  server.close()
          except:
              send_message(server, "Something went wrong. Please try again. :)\n")
              server.close()
      
      class RequestHandler(socketserver.BaseRequestHandler):
          def handle(self):
              start(self.request)
      
      if __name__ == '__main__':
          socketserver.ThreadingTCPServer.allow_reuse_address = True
          server = socketserver.ThreadingTCPServer(('0.0.0.0', 1337), RequestHandler)
          server.serve_forever()
---
## Missons
1. Find the first flag
2. Find the second flag

---
## Performance

## 1. Find the first flag
### Connect to the target using Netcat

    root@ip-10-10-78-98:~# nc 10.10.213.102 1337
    This XOR encoded text has flag 1: 201d082c004534293904312d3116040061263c13353b37641118193c3f2506213c6705062d0a250d
    What is the encryption key?

The clue: 201d082c004534293904312d3116040061263c13353b37641118193c3f2506213c6705062d0a250d

Normally, a THM flag has a format starting with THM{, so it can be used to decode the flag.

### Use Cyberchef

Cyberchef - Convert THM{ to Hex to identify how many bytes it is in the flag

    Input 
    THM{
    
    Output
    54 48 4d 7b

THM{ is 4 bytes, so the first 4 bytes in the code represents for THM{.

The first 4 bytes in 201d082c004534293904312d3116040061263c13353b37641118193c3f2506213c6705062d0a250d is 

    201d082c

Cyberchef - Encode THM{ to XOR code with the 201d082c (HEX)

    tUEW

Cyberchef - Decode the XOR encoded text

The source code mentioned "string.ascii_letters + string.digits, k=5", which means the key has 5 letters and digits. Therefore, guessing the last one in the key is not hard!

      Input: 
      
      201d082c004534293904312d3116040061263c13353b37641118193c3f2506213c6705062d0a250d
      
      Recipe:
      - From Hex
      - Xor
      
        Key: tUEW and one more digit/letter (UTF8) -> guessing (a,b,c,1,2,3,4,....)
      
        tUEWp-> worked! This is also the encryption key!!!
      
      Output
      The result of baking this recipe will reveal the first flag!

## 2. Find the second flag

The encryption key is tUEWp (found in the first task).

The XOR encoded text always changes for each netcat time (The source code showed how it would be changed). That is why you should be careful to put the key in the same session.

I did not, so lesson learned! I have to redo task 1 again to find a new encryption key and put it in the right session.

### Connect to the target again and find the 2nd flag

      root@ip-10-10-78-98:~# nc 10.10.213.102 1337
      This XOR encoded text has flag 1: 2d300f3d1448192e28103c003607100d4c212d07381630750515343b2e310b0c3b76110b000d3419

Now I have the new encoded text. I used the same technique as I did in the first task and found the key: yxBFd

      This XOR encoded text has flag 1: 2d300f3d1448192e28103c003607100d4c212d07381630750515343b2e310b0c3b76110b000d3419
      What is the encryption key? yxBFd

After inputting the key, the second flag will be revealed!





  
  










