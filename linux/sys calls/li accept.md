### accept (syscall)
-  accepting incomming connections request on the server side with a [[li socket]]
- [[li syscall]] for accepting the first connection request on the queue of pending connections of a [[li socket]] that is
	- of connectin based [[li socket]] types (`SOCK_STREAM` and `SOCK_SEQPACKET`)
	- on the server side
	-  in passiv mode/listening ([[li listen]] was called before)
- returns a new [[li socket]] [[li file descriptor]] in a connected state while the listening [[li socket]] is uneffected and continues listening
```C
int accept(
	sockfd, // listening socket file descriptor
	addr, // empty pointer that is filled with the peers adress
) // -> new connected socket file descriptor
```

