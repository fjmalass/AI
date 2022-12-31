# Encryption Thoughts

## Infrastructure
* David Malan (Harvard) [pdf](https://cs.harvard.edu/malan/publications/secon04.pdf)

## Python encrypted transfer
```
from Crypto.Cipher import AES
import socket
import os
import tqdm

## needs 16 bytes
key   = b"RhyptRulesNeed16"
nonce = b"RhyptRules_Nonce"
cipher = AES.new(key, AES.MODE_EAX, nonce)
text = "Hello World"

# Sender
ciphertext = cipher.encrypt(text)
# Receiver
plaintext = cipher.decrypt(ciphertext)

################
# sending script
################
# TCP socket creation connection to localhost
client =  socket.socket(socke.AF_INET, socket.SOCK_STREAM)
client.connect(("localhost", 9999))

filesize= os.path.getsize(<file>)
with open("file", "rb") as f:
  data = f.read()
encrypted = cipher.encrypt(data)

# Send meta meta data (filename, size), encrypted, <end>
client.send("file.text".encode()) # need to convert to bytes
client.send(str(file_size).encode()) # need to convert to bytes
client.sendall(data)# need to convert to bytes
client.send(b"<End>")# need to convert to bytes
client.close

################
# receiving script
################
server =  socket.socket(socke.AF_INET, socket.SOCK_STREAM)
server.connect(("localhost", 9999))
server.listen()

# only accept one connection 
client, addr = server.accept()
file_name = client.recv(1024).decode()
file_size = client.recv(1024).decode()
file = open(f"{file_name}.recv , "wb")
done = False
progress_bar = tqdm.tdqm(unit="B", unit_scale=True, unit_division=1000, total=int(file_size))

file_bytes = b""
while not done:
  data = client.recv(1024)
  if file_bytes[-5:] == b"<END>"
    done = True
  else:
    file_bytes += data
  progress_bar.update(1024)
file.write(cipher.decrypt(file_bytes[:-5]))
file.close()
client.close()
server.close()
```
