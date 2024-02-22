### recv (syscall)
- [[li syscall]] for reciving `len` bytes from one [[li connection based socket]] that was sent by another [[li connection based socket]] (`SOCK_STREAM` and `SOCK_SEQPACKAGE`) when both are in a connected state
- the message is writtien to the [[li virtual memory]] starting at adress `buff` 
- similar to the [[li read]] api for a general [[li file descriptor]] but more powerfull because of the additional `flags`
- specific for [[li socket]] [[li file descriptor]] (in a connected state)
- wrapper around [[li recvmsg]] 
	→ will revice the bytes and build a `msg` struct and send it with [[li recvmsg]]

```C
int recv(
	sockfd, // socket file discriptor
	buff,  // vm adress to save the incomming data
	len,  // number of bytes to recive
	flags,  // additional options
) // -> length of recived message
```


## related

![[li read#read (syscall)]]