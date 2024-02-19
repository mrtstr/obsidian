### li connect (syscall)
- [[li syscall]] for initiating a connection on an existing [[li socket]]
- if the [[li socket]] type is `SOCK_DGRAM` the adress will be the default adress to send to and the only adress to reciev from but no conenction is created immediately
- if the [[li socket]] type is `SOCK_STREAM` the connection to the address will be created immediately
```C
connect(
	sockfd, // file descriptor for the socket
	sockadd, // adress to connect to *
) // -> return code
```
