## [[li conection less socket]]
- [[li socket|socket types]] `SOCK_DGRAM` 
- no connection established between [[server]] and [[client]] before sending packages
- can be [[li unix domain socket]] too but is usualy a [[li internet domain socket]]

![[datagram#datagram]]


### socket creation
- no connection has to be established like with a [[li connection based socket]] ([[li listen]], [[li connect]], [[li accept]] not needed)
1) [[server]] and [[client]] create a [[li socket]] with type `SOCK_DGRAM` and the same domain

![[li socket (syscall)#socket (syscall)]]

2) the [[server]] binds an adress ([[port]] or path) to the [[li socket]]
![[li bind#bind (syscall)]]

### communication between [[li conection less socket]]
- `SOCK_DGRAM` [[li conection less socket]] can use [[li sendto]] and [[li recvfrom]] to send or revic from a specific adress (port or path)

![[li sendto#sendto (syscall)]]

![[li recvfrom#recvfrom (syscall)]]
- there is also a lower level api that transfers message structs and can provide more flexibilty: [[li sendmsg]], [[li recvmsg]]
- [[li sendto]], [[li recvfrom]] are just a wrapper around the userlaying [[li sendmsg]] and [[li recvmsg]]

![[li sendmsg#sendmsg (syscall)]]

![[li recvfrom#recvfrom (syscall)]]



![[dgram_sock_connectionless.gif]]


# anki

START
Basic
[[li conection less socket]]
- concept (3)
- properties of the connection (4)
- seps for creating and setup (with 3 [[li syscall]])
- communication between [[li conection less socket]] (with 4 [[li syscall]])
Back: 
## [[li conection less socket]]
- [[li socket|socket types]] `SOCK_DGRAM` 
- no connection established between [[server]] and [[client]] before sending packages
- can be [[li unix domain socket]] too but is usualy a [[li internet domain socket]]

### [[datagram]]
- connectionless
- unreliable (package loss and out of order)
- fixed length packages
- symetric
- e.g. [[user datagram protocol (UDP)]]


### socket creation
- no connection has to be established like with a [[li connection based socket]] ([[li listen]], [[li connect]], [[li accept]] not needed)
1) [[server]] and [[client]] create a [[li socket]] with type `SOCK_DGRAM` and the same domain

### socket (syscall)
- [[li syscall]] for creating an [[li socket]] endpoint 
- returns a [[li file descriptor]] that refers to that endpoint
```C
socket(
	domain,  
	type, 
) // → file descriptor
```

2) the [[server]] binds an adress ([[internet protocol (IP)]] or path) to the [[li socket]]
### bind (syscall)
- [[li syscall]] for binding an adress to and existing [[li socket]]
- while the [[server]] uses [[li bind]] to bind a adress to a [[li socket]] the [[client]] uses [[li connect]] to connect to the adress
- [[li unix domain socket]]: the adress is a filesystem path
- [[li internet domain socket]]: adress is a [[port]]
```C
int bind(
	sockfd, // file descriptor for the socket
	sockadd, // adress (path or ip) to bind to the file descriptor
) // -> return code
```

### communication between [[li conection less socket]]
- `SOCK_DGRAM` [[li conection less socket]] can use [[li sendto]] and [[li recvfrom]] to send or revic from a specific adress ([[port]] or path)

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

- there is also a lower level api that transfers message structs and can provide more flexibilty: [[li sendmsg]], [[li recvmsg]]
- [[li sendto]], [[li recvfrom]] are just a wrapper around the userlaying [[li sendmsg]] and [[li recvmsg]]

### sendmsg (syscall)
- [[li syscall]] for sending a message sturct from one [[li socket]] to another 
- the messagt struct `msg` is containing aditional information like desination adress and frags 
- for [[li connection based socket]] in a connected state or [[li conection less socket]]
- underlaying functions of [[li send]] and [[li sendto]]
	→ [[li send]] and [[li sendto]] will just create the `msg` struct based on the given adress ang flags 

```C
int send(
	sockfd, // socket file discriptor
	msg,  // msg struct
	flags,  // frags for additional options
) // -> return value
```

### recvmsg (syscall)
- [[li syscall]] for reciving a message sturct in one [[li socket]] that was sent by another 
- the messagt struct `msg` is containing aditional information like desination adress and frags 
- for [[li connection based socket]] in a connected state or [[li conection less socket]]
- underlaying functions of [[li recv]] and [[li recvfrom]]
	→ [[li recv]] and [[li recvfrom]] will just create the `msg` struct based after reciving the data

```C
int recvmsg(
	sockfd, // socket file discriptor
	msg,  // msg struct
	flags,  // frags for additional options
)
```

```C
struct msghdr {
   void         *msg_name;       /* Optional address */
   socklen_t     msg_namelen;    /* Size of address */
   struct iovec *msg_iov;        /* Scatter/gather array */
   size_t        msg_iovlen;     /* # elements in msg_iov */
   void         *msg_control;    /* Ancillary data, see below */
   size_t        msg_controllen; /* Ancillary data buffer len */
   int           msg_flags;      /* Flags (unused) */
}
```


### [[li socket]]
- endpoint in a two-way communication channel
- for sending data between [[li process|processes]] either [[li unix domain socket|locally]] or over [[li internet domain socket|network]]
- can use the generic [[li file descriptor]] api ([[li read]], [[li write]]) but have a specific api that provides more options ([[li send]], [[li recv]], [[li sendto]], [[li recvfrom]])

#### domain
- selects the protocol family which will be used for communication
	- `AF_UNIX` for [[li unix domain socket]] (like a local [[li file]])
	- `AF_INET`/`AF_INET6`: for [[li internet domain socket]] using the [[internet protocol (IP)]] protocol

#### type
- specifies communication semantics
- two different categorys that are avalibale for [[li unix domain socket]] and [[li internet domain socket]]
	- [[li connection based socket]] `SOCK_STREAM`, `SOCK_SEQPACKET`
	- [[li conection less socket]]: `SOCK_DGRAM`
- `SOCK_STREAM`: connection bases [[stream communication]] between a [[server]] and a [[client]]
- `SOCK_DGRAM`: [[datagram]] based connection less communication
- `SOCK_SEQPACKET`:  like `SOCK_STREAM` but each all of [[li read]] will return a full message
- `SOCK_RAW`: raw network protocol access (only for [[li internet domain socket]])

Tags: code linux
<!--ID: 1708600002635-->
END