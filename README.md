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
## SERVER.. 
```
import socket
s=socket.socket()
s.connect(('localhost', 8001))
while True:
    print(s.recv(1024).decode())  
    s.send("Acknowledgement Recived frome the server".encode())
```
## CLIENT..
```
import socket
s=socket.socket()
s.bind(('localhost', 8001))
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
## OUTPUT
## SERVER.. 
![Screenshot 2025-04-12 105903](https://github.com/user-attachments/assets/01b6a94e-d9e2-4e33-8bec-793fafcda8ea)
## CLIENT..
![Screenshot 2025-04-12 105914](https://github.com/user-attachments/assets/550023d9-ed41-4f5f-a915-dc47fa2ccfc7)
## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
