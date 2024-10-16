# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM

##client
```
import socket

HOST = '127.0.0.1'  
PORT = 65432       

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
  s.bind((HOST, PORT))
  s.listen()
  conn, addr = s.accept()
  with conn:
    print('Connected by', addr)
    while True:
      data = conn.recv(1024)
      if not data:
        break
      conn.sendall(data)
```
##sever
```
import socket

HOST = '127.0.0.1'  
PORT = 65432        

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
   s.connect((HOST, PORT))
   while True:
      message = input("Enter message to send to server: ")
      s.sendall(message.encode())
      data = s.recv(1024)
      print('Received', repr(data.decode()))
```
## OUPUT
![Screenshot 2024-10-16 114044](https://github.com/user-attachments/assets/38d41955-157d-4256-9ac5-6dbf370f0447)
![Screenshot 2024-10-16 114100](https://github.com/user-attachments/assets/1b86f421-d875-460f-b554-b7f38365ad23)

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
