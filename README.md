# 2a_Stop_and_Wait_Protocol

## Developed By : DHARAN ADITYA
## Register No  : 212223040035


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
# Client.py:
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

# server.py:
```
    import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT:
# Client :

![321844457-342905ca-15ca-46fd-a544-a5cd5021b69f](https://github.com/DharanAditya/2a_Stop_and_Wait_Protocol/assets/147473834/8afb5cb0-64fc-4bd7-a9cf-07321c8bf1a8)

# Server :
![321844475-92c0527e-e882-4b0a-abd3-2651c406fe89](https://github.com/DharanAditya/2a_Stop_and_Wait_Protocol/assets/147473834/f48911cc-5469-4d98-8e3f-756454157903)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
