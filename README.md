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
## SERVER
```
import socket
s=socket.socket()
s.bind(('localhost', 8001))
s.listen(1)
print("Waiting for connection...")
c, addr=s.accept()
print("Connected to", addr)
while True:
    clientMessage=c.recv(1024).decode()
    if clientMessage=="exit":
        print("Client disconnected")
        break
    print("Echo of Client >", clientMessage)
    reply = input("Server > ")
    c.send(reply.encode())
c.close()
s.close()
```
## CLIENT
```
import socket
s=socket.socket()
s.connect(('localhost', 8001))
while True:
    msg=input("Client > ")
    s.send(msg.encode())
    if msg=="exit":
        print("Disconnected")
        break
    print("Echo of Server >", s.recv(1024).decode())
s.close()
```
## OUPUT
SERVER

<img width="786" height="260" alt="Screenshot 2026-03-25 194713" src="https://github.com/user-attachments/assets/47747c91-e2e1-4b3b-b00a-25e6a9a59a26" />

CLIENT

<img width="1117" height="284" alt="Screenshot 2026-03-25 194727" src="https://github.com/user-attachments/assets/86b0e58f-0c85-4739-88bf-e3065f326c34" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
