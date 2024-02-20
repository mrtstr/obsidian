### listen (syscall)
- [[li syscall]] for marking an [[li socket]] [[li file descriptor]] as passiv 
	→ accepting incomming connection requests
- only for connectin based [[li socket]] types (`SOCK_STREAM` and `SOCK_SEQPACKET`) 
- done on the server side
```C
int listen(
	sockfd, // file descriptor
	backlog, // maximum length to which the queue of pending connections
) // -> return code
```

