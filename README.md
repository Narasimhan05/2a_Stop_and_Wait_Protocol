# 2a_Stop_and_Wait_Protocol
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
CLIENT:
import socket
s=socket.socket()
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
SERVER:
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
## OUTPUT
CLIENT:
![image](https://github.com/Narasimhan05/2a_Stop_and_Wait_Protocol/assets/132819871/fe532ccb-280d-42a6-8f25-c701e83a3e58)

SERVER:
![image](https://github.com/Narasimhan05/2a_Stop_and_Wait_Protocol/assets/132819871/d6b1d250-7071-4b4c-aeeb-f6c1df8fdea3)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
