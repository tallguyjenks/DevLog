

- [Article On This Project](https://medium.com/geekculture/build-your-own-file-transfer-app-using-python-within-5-minutes-56adffc7906b)
- Uses: [[os|import.os]], [[socket|import.socket]], [[tqdm|import.tqdm]]

## Server:

```python
import socket
import tqdm
import os

SERVER_HOST = "0.0.0.0"
SERVER_PORT = 5001
BUFFER_SIZE = 4096
SEPARATOR = "<SEPARATOR>"

s = socket.socket()
s.bind((SERVER_HOST, SERVER_PORT))
s.listen(10)
print(f"[*] Listening as {SERVER_HOST}:{SERVER_PORT}")
print("Waiting for the client to connect... ")
client_socket, address = s.accept()
print(f"[+] {address} is connected.")
received = client_socket.recv(BUFFER_SIZE).decode()
filename, filesize = received.split(SEPARATOR)
filename = os.path.basename(filename)
filesize = int(filesize)
progress = tqdm.tqdm(range(filesize), f"Receiving {filename}", unit="B", unit_scale=True, unit_divisor=1024)
with open(filename, "wb") as f:
  while True:
	  bytes_read = client_socket.recv(BUFFER_SIZE)
	  if not bytes_read:
		  break
	  f.write(bytes_read)
	  progress.update(len(bytes_read))
client_socket.close()
s.close()
```

## Client:

```python
import socket
import tqdm
import os

SEPARATOR = "<SEPARATOR>"
BUFFER_SIZE = 4096

s = socket.socket()
host = "192.168.1.109"
port = 5001
print(f"[+] Connecting to {host}:{port}")
s.connect((host, port))
print("[+] Connected to ", host)
filename = input("File to Transfer : ")
filesize = os.path.getsize(filename)
s.send(f"{filename}{SEPARATOR}{filesize}".encode())
#file = open(filename, 'wb') 

progress = tqdm.tqdm(range(filesize), f"Sending {filename}", unit="B", unit_scale=True, unit_divisor=1024)
with open(filename, "rb") as f:
  while True:
	  bytes_read = f.read(BUFFER_SIZE)
	  if not bytes_read:
		  break
	  s.sendall(bytes_read)
	  progress.update(len(bytes_read))
s.close()
```

## Tips:

> You can extend this code by adding more features to meet your own needs. These are only a few of them:

- Enable the server to receive multiple files from multiple clients at the same time using threads.
- Compress the file before sending it.
- Encrypt the file before sending it to ensure no one intercepting it will read it.
- To make sure we sent the files properly, use secure hashing algorithms. It will check the checksums of both files — the original sender file and the received file.
