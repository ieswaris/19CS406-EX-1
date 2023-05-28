# 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

# DATE : 08-03-2023

# AIM : 
To write a python program to perform stop and wait protocol


# ALGORITHM :
1.Start the program.

2.Get the frame size from the user

3.To create the frame based on the user request.

4.To send frames to server from the client side.

5.If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.

6.Stop the program

# CLIENT PROGRAM :
```
DEVELOPED BY:ESWARI S
REG NO:212221220012
```
```
import socket
s=socket.socket()
s.bind(('localhost',8080))
s.listen(5)
c,addr=s.accept()
while True:
   i=input("ENter a data:")
   c.send(i.encode())
   ack=c.recv(1024).decode()
   if ack:
   	print(ack)
   	continue
   else:
   	c.close()
   	break
 ```
 # SERVER PROGRAM
```
import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
	print(s.recv(1024).decode())
	s.send("Recieved".encode())
 ```
# OUTPUT:
# SERVER OUTPUT:
![image](https://github.com/ieswaris/19CS406-EX-1/assets/127847210/1e638cd8-e364-4e2f-a49e-22e78ed9531b)

# CLIENT OUTPUT:
![image](https://github.com/ieswaris/19CS406-EX-1/assets/127847210/315c8b77-67d2-4577-b5ce-b03477a8bf5c)

# RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.

