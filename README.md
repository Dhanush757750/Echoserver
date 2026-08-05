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
## Server code:
```
# echo-server.py


import socket

HOST = "127.0.0.1"
PORT = 65432

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    print("Server is waiting for connection...")

    conn, addr = s.accept()

    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            print("Received from client:", data.decode())
            conn.sendall(data)

```
## Client code:
```
# echo-client.py


import socket

HOST = "127.0.0.1"
PORT = 65432

message = "212224040066 DHANUSH C"

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(message.encode())
    data = s.recv(1024)

print("Received from server:", data.decode())

```
## OUTPUT:

<img width="1919" height="1199" alt="ex01a" src="https://github.com/user-attachments/assets/9b9dba05-4514-4471-b6ef-c732fc4286b2" />
<img width="1919" height="1199" alt="ex01b" src="https://github.com/user-attachments/assets/28c9c624-7e04-4791-a4f3-2d6082018111" />

## RESULT:
The program is executed successfully
