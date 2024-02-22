### recvfrom (syscall)
- [[li syscall]] for reciving `len` bytes with a [[li socket]] that was sent by [[li socket]] with a certain `src_addr`
- similar to [[li recv]] but with the option to provide a destination adress `src_addr` specificly for [[li conection less socket]] (`SOCK_DGRAM`) 
- can also be used for [[li connection based socket]] in a connected state but `src_addr` will be ignored in this case which is equivaltent to [[li recv]]
- wrapper around [[li recvmsg]] 

```C
int recvfrom(
	sockfd, // socket file discriptor
	buff,  // vm adress to save the data
	len,  // number of bytes to recive
	flags,  // additional options
	src_addr,  // adress of the socket (ip of path) ro recive the data from
) // -> return value
```