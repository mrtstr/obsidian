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


# Anki
START
Basic
[[li send]] vs [[li sendto]] [[li syscall]]

Back: 
- send is used mainly for [[li connection based socket]] (`SOCK_STREAM` and `SOCK_SEQPACKET`) to send over a established connection
- [[li sendto]] for sending a package between [[li conection less socket|conection less sockets]] (`SOCK_DGRAM`) to a sertain adress
- [[li sendto]] can be used instead of [[li send]] with [[li connection based socket]] using null as adress `sendto(sockfd, buf, len, flags, NULL, 0)` (but it does not make sense)

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

Tags: code linux

END