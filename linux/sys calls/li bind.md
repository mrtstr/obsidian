### bind (syscall)
- [[li syscall]] for binding an adress to and existing [[li socket]]
- while the [[server]] uses [[li bind]] to bind a adress to a [[li socket]] the [[client]] uses [[li connect]] to connect to the adress
- in case of a [[li unix domain socket]] [[li bind]] can be used to bind the socket to a  filesystem path
```C
bind(
	sockfd, // file descriptor for the socket
	sockadd, // adress to bind to the file descriptor
) // -> return code
```