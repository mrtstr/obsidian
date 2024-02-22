### sendto (syscall)
- [[li syscall]] for sending `len` bytes from one [[li socket]] to another [[li socket]] with a certain `dest_addr`
- similar to [[li send]] but with the option to provide a destination adress `dest_addr` specificly for [[li conection less socket]] (`SOCK_DGRAM`) 
- can also be used for [[li connection based socket]] in a connected state but `dest_addr` will be ignored in this case which is equivaltent to [[li send]]
- wrapper around [[li sendmsg]] 
	→ will build a `msg` struct and send it with [[li sendmsg]]

```C
int sendto(
	sockfd, // socket file discriptor
	buff,  // vm adress of data to write
	len,  // number of bytes to write
	flags,  // additional options
	dest_addr,  // adress of the recieving socket (ip of path)
	addrlen,  // vm adress of data to write
) // -> return value
```