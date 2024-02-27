# Ethical-Hacking-Techniques---19CS417-
Ethical Hacking Techniques - 19CS417 
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
### echo-server.py
```py
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
### echo-client.py
```py
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
### echo-server.py

![exp1server](https://github.com/Skanthasishanth/Ethicka-Hacking-Techniques---19CS417-/assets/118298456/541a8afe-b8f8-4db1-ac47-edcc624658cd)
<br>
<br>
### echo-client.py

![exp1client](https://github.com/Skanthasishanth/Ethicka-Hacking-Techniques---19CS417-/assets/118298456/b5e528fb-a33b-4b0c-b8aa-616626758989)


## RESULT:
The program is executed successfully
