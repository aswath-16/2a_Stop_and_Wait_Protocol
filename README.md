# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
NAME:- ASWATH RAGAVAN MG
REG NO:- 212225230028
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
SERVER
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
CLIENT
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
<img width="1901" height="1078" alt="Screenshot 2026-11-25 082057" src="https://github.com/user-attachments/assets/7f8117e5-1b97-4cac-91dd-0b3fad16de5f" />
<img width="1917" height="1077" alt="Screenshot 2026-11-25 082111" src="https://github.com/user-attachments/assets/c9ef966c-39e7-453b-b9a2-1f8b43b54601" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
