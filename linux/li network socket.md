## [[li network socket]]
[[linux/li socket]]
- in calse of a [[li network socket]] the [[server]] binds the adress to the [[li socket]] while the [[client]] will connect to the adress using [[li connect]] 
- Each socket within the network has a unique name associated with it called a socket descriptor


[[stream communication]] and [[datadram]]

As with file access, user processes ask the operating system to create a socket when one is needed
The system returns an integer, the socket descriptor (sd), that the application uses every time it wants to refer to that socket.
The main difference between sockets and files is that the operating system binds file descriptors to a file or device when the open() call creates the file descriptor.


Sockets behave in some respects like UNIX files or devices, so they can be used with such traditional operations as read() or write()


-   Internet Protocol Sockets, which are part of the Internet Address Family (AF_INET for IPv4 and AF_INET6 for IPv6)


AF_INET and AF_INET6 sockets provide a means of communicating between application programs that are on different systems using the Transport Control Protocol provided by a TCP/IP product. This socket family supports both stream and datagram sockets. Each of these socket types is described in the next section.


