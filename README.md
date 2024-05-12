## EXP.NO  2B IMPLEMENTATION OF SLIDING WINDOW PROTOCOL

## NAME: VISWANADHAM VENKATA SAI SRUTHI
## REG NO: 212223100061

## AIM
To implement the sliding window protocal using Python.

## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
## Client:

```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
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
## Server:

```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
    print(s.recv(1024).decode())
    s.send("acknowledgement recived from the server".encode())
```

## OUPUT
## Client:

![image](https://github.com/sruthiviswanadham/2b_SLIDING_WINDOW_PROTOCOL/assets/151760421/7f36b9f3-13d9-4ab4-99c6-c92a60fe6b17)

## Server:

![image](https://github.com/sruthiviswanadham/2b_SLIDING_WINDOW_PROTOCOL/assets/151760421/ad0a8e0c-58bd-431c-8550-0211e2ca35ff)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
