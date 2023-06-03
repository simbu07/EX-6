## EX-6 IMPLEMENTATION OF PING COMMAND
### DATE :10-04-2023

### AIM :

To write the python program for simulating ping command.

### ALGORITHM :
```
1.start the program.
2.Include necessary package in java.
3.To create a process object p to implement the ping command.
4.declare one Buffered Reader stream class object.
6.Get the details of the server
7.length of the IP address.
8.time required to get the details.
9.send packets, receive packets and lost packets.
10.minimum, maximum and average times.
11.print the results.
12.Stop the program.
```
### PROGRAM :
```
Developed By: Silambarasan K
REg No: 212221230101
```
### CLIENT :
```py
import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    hostname=c.recv(1024).decode()
    try:
        c.send(str(ping(hostname, verbose=False)).encode())
    except KeyError:
        c.send("Not Found".encode())
```
### SERVER :
```py
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter the website you want to ping ")
    s.send(ip.encode())
    print(s.recv(1024).decode())
```
### OUTPUT :

### CLIENT :

![image](https://user-images.githubusercontent.com/122860624/243069244-147fb995-cf9e-4442-bc28-c7981edebcca.png)

### SERVER:

![image](https://user-images.githubusercontent.com/122860624/243069409-cfa11b4e-8d84-4467-b55c-2379b3db40b3.png)

### RESULT :

Thus, the python program for simulating ping command was successfully executed.
