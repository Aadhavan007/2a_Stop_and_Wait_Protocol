# 2a_Stop_and_Wait_Protocol
## NAME: M AADHAVAN NAGARAJAN
## REGISTER NUMBER: 212225040001
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
SERVER PROGRAM:
```

import socket

s = socket.socket()
s.bind(('localhost', 8001))
s.listen(5)

print("Server is waiting for client...")

c, addr = s.accept()
print("Client connected:", addr)

while True:
    data = c.recv(1024).decode()

    if not data:
        break

    print(data)
    c.send("Acknowledgement Received".encode())

c.close()
s.close()
```
CLIENT PROGRAM:
```
import socket

s = socket.socket()
s.connect(('localhost', 8001))

while True:
    i = input("Enter a data: ")
    s.send(i.encode())

    ack = s.recv(1024).decode()

    if ack:
        print(ack)
    else:
        s.close()
        break

```
## OUTPUT
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ecf3544a-5e5a-46c6-8ff6-7ac2da1a0af5" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e3403802-39b0-4610-b543-41b3251d1539" />


## RESULT
Thus python program to perform stop and wait protocol was successfully executed.
