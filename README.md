# EXP: 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM:
To write a python program to perform sliding window protocol
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
```
Developed by : SUDHIR KUMAR .R
Register number : 212223230221
```
### CLIENT:
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
### SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("acknowledgement recieved from the server".encode())
```
## OUPUT:

### CLIENT:

![exp4-1](https://github.com/Sudhirr5/2b_SLIDING_WINDOW_PROTOCOL/assets/139332214/b922728e-e8a8-42d8-9dfd-401799b12c99)

### SERVER:

![exp4-2](https://github.com/Sudhirr5/2b_SLIDING_WINDOW_PROTOCOL/assets/139332214/30cb5da1-aec8-418f-9e3c-4a30da3f36fe)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
