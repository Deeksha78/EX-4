# EX-4 IMPLEMENTATION OF ADDRESS RESOLUTION PROTOCOL (ARP)

DATE :30-03-2023

AIM :To write a python program for simulating ARP protocols using TCP.


ALGORITHM :

Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.

Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.


PROGRAM :

CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"};
while True:
 ip=c.recv(1024).decode()
 try:
 c.send(address[ip].encode())
 except KeyError:
 c.send("Not Found".encode())
 ```
 
SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
REG NO:
 ip=input("Enter logical Address : ")
 s.send(ip.encode())
 print("MAC Address",s.recv(1024).decode())
```

OUTPUT :

CLIENT:


![Screenshot from 2023-05-25 11-30-51](https://github.com/sujathamohankumar/EX-4/assets/128116204/4645afdc-8e07-4848-9691-4eef578cfd81)



SERVER:

![Screenshot from 2023-05-25 11-31-08](https://github.com/sujathamohankumar/EX-4/assets/128116204/33e5d0e3-744a-4bc0-9ec9-f26b631c0f15)





RESULT :
Thus, the python program for simulating ARP protocols using TCP was successfully
executed.


