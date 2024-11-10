# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
### NAME: KRISHNA KUMAR R
### REG.NO:212223230107
## AIM
To write a python program for Implementation of sliding Window Protocol.
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
### Client
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send: "))
l=list(range(size))
s=int(input("Enter Window Size: "))
st=0
i=0
while True:
    while(i<len(l)):
        st+=s
        c.send(str(l[i:st]).encode())
        ack=c.recv(1024).decode()
        if ack:
            print(ack)
            i+=s
```
### Server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## OUPUT
### Client
![Screenshot 2024-09-10 085929](https://github.com/user-attachments/assets/bf4cfbd3-9220-4570-bf83-66ebdcef795a)

### Server
![Screenshot 2024-09-10 085953](https://github.com/user-attachments/assets/e55b7764-16ff-47e7-aff9-bb4482a952ab)


## RESULT
Thus, python program to perform sliding Window Protocol was successfully executed
