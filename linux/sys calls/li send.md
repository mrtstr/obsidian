### send (syscall)
- [[li syscall]] for sending `len` bytes from the [[li virtual memory]] starting at adress `buff` from one [[li connection based socket]] (`SOCK_STREAM` and `SOCK_SEQPACKAGE`) to onther
- similar to the [[li write]] api for a general [[li file descriptor]] but more powerfull because of the additional `flags`
- specific for [[li socket]] [[li file descriptor]] (in a connected state)
- wrapper around [[li sendmsg]] 
	→ will build a `msg` struct and send it with [[li sendmsg]]

```C
int send(
	sockfd, // socket file discriptor
	buff,  // vm adress of data to write
	len,  // number of bytes to write
	flags,  // additional options
) // -> return value
```