### bind (syscall)
- [[li syscall]] for binding an adress to and existing [[li socket]]
- while the [[server]] uses [[li bind]] to bind a adress to a [[li socket]] the [[client]] uses [[li connect]] to connect to the adress
- [[li unix domain socket]]: the adress is a filesystem path
- [[li internet domain socket]]: adress is a [[IP]] adress
```C
int bind(
	sockfd, // file descriptor for the socket
	sockadd, // adress (path or ip) to bind to the file descriptor
) // -> return code
```