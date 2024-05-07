# Ethicka-Hacking-Techniques---19CS417
# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
**server.py:**
```
import socket
HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024).decode()
            if not data:
                break
            conn.sendall(data.encode())
```     
**client.py:**
```
import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    while True:
       s.sendall(input().encode()) 
       data = s.recv(1024).decode()
       print(f"Received {data!r}")
```

## OUTPUT:
### server.py
![Screenshot (53)](https://github.com/Sahithya373/Ethicka-Hacking-Techniques---19CS417-/assets/147017926/ac5fa54d-0bd9-454c-831e-b4f2c280f741)


### client.py

![Screenshot (54)](https://github.com/Sahithya373/Ethicka-Hacking-Techniques---19CS417-/assets/147017926/1deb0e6e-65e8-4aa7-bb4e-d3d5568ff85c)



## RESULT:
The program is executed successfully
