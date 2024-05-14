## EXP-2a                              Stop and Wait Protocol

NAME:RAMYA.P

REGISTER NUMBER: 212223240137

DEPARTMENT: AIML

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
## CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
 i=input("Enter a data: ")
 c.send(i.encode())
 ack=c.recv(1024).decode()
 if ack:
   print(ack)
   continue
 else:
   c.close()
   break
```

## SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT
## CLIENT:
![image](https://github.com/23014107/2a_Stop_and_Wait_Protocol/assets/151625620/645d500f-cb52-4389-acfa-c94ee650bfee)

## SERVER:
![image](https://github.com/23014107/2a_Stop_and_Wait_Protocol/assets/151625620/68d72903-0fec-4e4c-a869-04f2cc1122a9)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
