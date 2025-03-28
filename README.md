# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
```
import socket

s = socket.socket()
s.connect(('127.0.0.1', 8000))  # Using 127.0.0.1 for reliable local connection

while True:
    msg = input("Client > ")
    if not msg:
        break  # Exit loop if the input is empty
    s.send(msg.encode())

    server_response = s.recv(1024).decode()
    if not server_response:
        break  # Exit loop if the server closes the connection
    print("Server >", server_response)

s.close()
import socket

s = socket.socket()
s.bind(('127.0.0.1', 8000))  # Using 127.0.0.1 for IPv4 compatibility
s.listen(1)

print("Server is waiting for a connection...")
c, addr = s.accept()
print(f"Connected to {addr}")

while True:
    client_message = c.recv(1024).decode()
    if not client_message:
        break  # Exit loop if the client disconnects
    print("Client >", client_message)

    msg = input("Server > ")
    if not msg:
        break  # Exit loop if the input is empty
    c.send(msg.encode())

c.close()
s.close()

```
## OUPUT
![3b idle 2](https://github.com/user-attachments/assets/36792229-31b0-4d61-a2a9-e8248f98765c)
![3b idle 1](https://github.com/user-attachments/assets/2b8794de-a3a4-4da3-ba67-95b023976a31)
![3b client](https://github.com/user-attachments/assets/a62abba6-86e3-4d18-9d62-896bec79afbe)
![3bserver](https://github.com/user-attachments/assets/f5dba7de-5551-4e83-85f5-d47cbf89841f)



## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
