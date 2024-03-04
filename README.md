# Ethicka-Hacking-Techniques---19CS417-
Ethicka Hacking Techniques - 19CS417 
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

# Server code

### echo-server.py
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
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)

```

# Client Code

### echo-client.py
```
import socket
HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)
print(f"Received {data!r}")
```



## OUTPUT:
### echo server output
![VirtualBox_mine_05_03_2024_01_16_11](https://github.com/Kaviarasu510/Echoserver/assets/119392695/227ac3d0-b052-457a-acce-dd59e7eb7e49)

### echo client output
![VirtualBox_mine_05_03_2024_01_16_19](https://github.com/Kaviarasu510/Echoserver/assets/119392695/f4f303ff-17d0-443e-93ec-b7e8127224b8)

## RESULT:
The program is executed successfully

