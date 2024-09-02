# Ex-01 Echoserver
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
## SERVER:
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

## CLIENT:
```
import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"PAVITHRA R-212222230106")
    data = s.recv(1024)


print(f"Received {data!r}")
```
## OUTPUT:
## SERVER:

![image](https://github.com/user-attachments/assets/1237a0fa-dd96-49a4-a00b-3f4558e068ff)


## CLIENT:

![image](https://github.com/user-attachments/assets/1dc5b713-0c7b-4641-9fa9-770238d81341)



## RESULT:
The program is executed successfully
