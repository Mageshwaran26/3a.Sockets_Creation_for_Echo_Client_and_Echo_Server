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
SERVER

     import socket
     server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
     host = '127.0.0.1'  
     port = 12345        
     server_socket.bind((host, port))
     server_socket.listen(1)
     print("Server is listening on port", port)
     conn, addr = server_socket.accept()
     print("Connected by", addr)
     while True:
         data = conn.recv(1024).decode()
         if not data:
             break
         print("Received from client:", data)
         conn.send(data.encode())  
     conn.close()
     server_socket.close()
     print("Server closed.")

CLIENT

     import socket
     client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
     host = '127.0.0.1'
     port = 12345
     
     client_socket.connect((host, port))
     
     while True:
         message = input("Enter message (type 'bye' to exit): ")
         if message.lower() == 'bye':
             break
         client_socket.send(message.encode())
         data = client_socket.recv(1024).decode()
         print("Received from server:", data)
     
     
     client_socket.close()
     print("Client closed.")
## OUPUT
SERVER

<img width="661" height="318" alt="image" src="https://github.com/user-attachments/assets/43f181ff-1cf1-427d-8150-2f5aaea0ab17" />

CLIENT

<img width="805" height="363" alt="image" src="https://github.com/user-attachments/assets/954092d5-3c47-41e3-ad9c-c7d851515790" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
