# Socket-Programming?
**Is a way of connecting two nodes on a network to communicate with each other.**
***Sockets may be implemented over a number of different channel types: Unix domain sockets, TCP, UDP, and so on.***

## Sockets' vocabulary:
- `Domain` -> The family of protocols that is used as the transport mechanism. These values are constants such as AF_INET, PF_INET, PF_UNIX, PF_X25, and so on.
    - Ex: family=socket.AF_INET -> defines the address family that this socket can accept – only IPv4 addresses. 
- `Type` -> The type of communications between the two endpoints, typically SOCK_STREAM for connection-oriented protocols and SOCK_DGRAM for connectionless protocols.
    - Ex: type=socket.SOCK_STREAM -> defines that the socket accepts only TCP connections.
- `protocol` -> Typically zero, this may be used to identify a variant of a protocol within a domain and type.
- `hostname` -> The identifier of a network interface
    - A string, which can be a host name, a dotted-quad address, or an IPV6 address in colon (and possibly dot) notation
    - A string "<broadcast>", which specifies an INADDR_BROADCAST address.
    - A zero-length string, which specifies INADDR_ANY, or
    - An Integer, interpreted as a binary address in host byte order.
- `port` -> Each server listens for clients calling on one or more ports. A port may be a Fixnum port number, a string containing a port number, or the name of a service.

**The socket Module:**
***s = socket.socket (socket_family, socket_type, protocol=0)***

## Server Socket Methods:
- `s.bind()` -> This method binds address (hostname, port number pair) to socket.
- `s.listen()` -> This method sets up and start TCP listener.	
- `s.accept()` -> This passively accept TCP client connection, waiting until connection arrives (blocking).

## Client Socket Methods:
- `s.connect()` -> This method actively initiates TCP server connection.

## General Socket Methods:
- `s.recv()` -> This method receives TCP message
- `s.send()` -> This method transmits TCP message
- `s.recvfrom()` -> This method receives UDP message
- `s.sendto()` -> This method transmits UDP message
- `s.close()` -> This method closes socket
- `socket.gethostname()` -> Returns the hostname.

**A list of some important modules in Python Network/Internet programming.**

| Protocol 	 |   Common function    |    Port No    |    Python module                |
|------------|----------------------|---------------|---------------------------------|
| HTTP 	     |   Web pages 	        |    80 	    |     httplib, urllib, xmlrpclib  |
| NNTP 	     |   Usenet news 	    |    119 	    |     nntplib                     |
| FTP 	     |   File transfers     |	 20 	    |     ftplib, urllib              |
| SMTP 	     |   Sending email 	    |    25 	    |     smtplib                     |
| POP3 	     |   Fetching email     |    110 	    |     poplib                      |
| IMAP4 	 |   Fetching email     |	 143 	    |     imaplib                     |
| Telnet 	 |   Command lines 	    |    23 	    |     telnetlib                   |
| Gopher 	 |   Document transfers | 	 70 	    |     gopherlib, urllib           |

***the client acts as the requester, where it requests some data. The server acts as the listener and provides the client the requested data as the response.***

**resource:**
- https://www.freecodecamp.org/news/socket-programming-in-python/
- https://www.tutorialspoint.com/python/python_networking.htm