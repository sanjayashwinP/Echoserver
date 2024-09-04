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

## CLIENT SIDE:
```
mport socket
HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Sanjay Ashwin P  212223040181")
    data = s.recv(1024)
print(f"Received {data!r}")
```
## SERVER SIDE:
```
import socket
HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    try:
        s.bind((HOST, PORT))
    except Exception as e:
        print(f"Error binding to {HOST}:{PORT}: {e}")
        exit()
    s.listen()
    print(f"Listening on {HOST}:{PORT}...")
    try:
        conn, addr = s.accept()
    except Exception as e:
        print(f"Error accepting connection: {e}")
        exit()
    with conn:
        print(f"Connected by {addr}")
        while True:
            try:
                data = conn.recv(1024)
                if not data:
                    break
                conn.sendall(data)
            except Exception as e:
                print(f"Error receiving/sending data: {e}")
                exit()
```
## OUTPUT:
## SERVER SIDE:
![Screenshot 2024-09-04 102704](https://github.com/user-attachments/assets/4d703fd2-b6cd-443b-835d-466dc20e50b8)


## CLIENT SIDE:

![Screenshot 2024-09-04 102614](https://github.com/user-attachments/assets/e9bdd6e6-7e6e-44e5-9282-1ec8813b80e0)

## RESULT:
The program is executed successfully
