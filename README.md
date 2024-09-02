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
### Client :
```python
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
### Server : 
```python
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
print(s.recv(1024).decode())
s.send("Acknowledgement Recived".encode())

```

## OUTPUT

![Screenshot 2024-09-02 181154](https://github.com/user-attachments/assets/c2e8e935-2c49-4867-8cdb-d1ec91d685ba)


![image](https://github.com/user-attachments/assets/ca808e3e-17e9-47b3-9d49-12c79f1b2ac8)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
