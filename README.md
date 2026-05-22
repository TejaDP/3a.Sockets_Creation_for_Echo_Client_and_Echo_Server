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
```
# Echo Server Program

import socket

# Create socket object
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Define host and port
host = '127.0.0.1'
port = 5000

# Bind the socket with host and port
server_socket.bind((host, port))

# Listen for incoming connections
server_socket.listen(1)

print("Echo Server is waiting for connection...")

# Accept client connection
client_socket, addr = server_socket.accept()

print("Connected to:", addr)

while True:
    # Receive message from client
    data = client_socket.recv(1024).decode()

    # If no data received, break loop
    if not data:
        break

    print("Client:", data)

    # Send same message back to client
    client_socket.send(data.encode())

# Close sockets
client_socket.close()
server_socket.close()



 chat_client.py

import socket

# Create socket
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Server details
host = '127.0.0.1'
port = 5000

# Connect to server
client_socket.connect((host, port))

print("Connected to server")

while True:
    # Send message to server
    message = input("Client: ")
    client_socket.send(message.encode())

    # Exit if client says bye
    if message.lower() == "bye":
        break

    # Receive message from server
    server_message = client_socket.recv(1024).decode()
    print("Server:", server_message)

    # Exit if server says bye
    if server_message.lower() == "bye":
        break

# Close connection
client_socket.close()
```
## OUPUT
<img width="1794" height="982" alt="Screenshot 2026-05-22 085615" src="https://github.com/user-attachments/assets/39c86909-8f27-4e8a-8751-e951b5700661" />


## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
