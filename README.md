2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
AIM
ALGORITHM:
Start the program.
Get the frame size from the user
To create the frame based on the user request.
To send frames to server from the client side.
If your frames reach the server it will send ACK signal to client
Stop the Program
PROGRAM
Developed by : VINNUSH KUMAR L S

Reg no : 212223230244

Client.py


import socket
from datetime import datetime
 
s=socket.socket()
 
s.bind(('localhost',8080))
 
s.listen(5)
c,addr=s.accept()
print("Client Address : ",addr)
 
now = datetime.now()
 
c.send(now.strftime("%d/%m/%Y %H:%M:%S").encode())
ack=c.recv(1024).decode()
 
if ack:
    print(ack)
c.close()
Server.py


import socket 
s=socket.socket() 
s.connect(('localhost',8080)) 
print(s.getsockname()) 
print(s.recv(1024).decode()) 
s.send("acknowledgement recived from the server".encode()) 

OUPUT
Screenshot 2025-04-12 105945

RESULT
Thus, python program to perform stop and wait protocol was successfully executed
