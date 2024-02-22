## [[li socket]]
- endpoint in a two-way communication channel
- for sending data between [[li process|processes]] either [[li unix domain socket|locally]] or over [[li internet domain socket|network]]
- can use the generic [[li file descriptor]] api ([[li read]], [[li write]]) but have a specific api that provides more options ([[li send]], [[li recv]], [[li sendto]], [[li recvfrom]])

### domain
- selects the protocol family which will be used for communication
	- `AF_UNIX` for [[li unix domain socket]] (like a local [[li file]])
	- `AF_INET`/`AF_INET6`: for [[li internet domain socket]] using the [[IP]] protocol

![[1 ekw1o4xE_7ew9kYh6tVkCA.webp]]

### type
- specifies communication semantics
- two different categorys that are avalibale for [[li unix domain socket]] and [[li internet domain socket]]
	- [[li connection based socket]]: `SOCK_STREAM`, `SOCK_SEQPACKET`
	- [[li conection less socket]]: `SOCK_DGRAM`
- `SOCK_STREAM`: connection bases [[stream communication]] between a [[server]] and a [[client]]
- `SOCK_DGRAM`: [[datagram]] based connection less communication
- `SOCK_SEQPACKET`:  like `SOCK_STREAM` but each all of [[li read]] will return a full message
- `SOCK_RAW`: raw network protocol access (only for [[li internet domain socket]])



# anki

START
Basic
[[li socket]]
- concept
- domain (2)
- types (4)

Back: 
## [[li socket]]
- endpoint in a two-way communication channel
- for sending data between [[li process|processes]] either [[li unix domain socket|locally]] or over [[li internet domain socket|network]]
- can use the generic [[li file descriptor]] api ([[li read]], [[li write]]) but have a specific api that provides more options ([[li send]], [[li recv]], [[li sendto]], [[li recvfrom]])

### domain
- selects the protocol family which will be used for communication
	- `AF_UNIX` for [[li unix domain socket]] (like a local [[li file]])
	- `AF_INET`/`AF_INET6`: for [[li internet domain socket]] using the [[IP]] protocol

![[socket_unix_vs_internet.jpg]]


### type
- specifies communication semantics
- two different categorys that are avalibale for [[li unix domain socket]] and [[li internet domain socket]]
	- [[li connection based socket]]: `SOCK_STREAM`, `SOCK_SEQPACKET`
	- conection less: `SOCK_DGRAM`
- `SOCK_STREAM`: connection bases [[stream communication]] between a [[server]] and a [[client]]
- `SOCK_DGRAM`: [[datagram]] based connection less communication
- `SOCK_SEQPACKET`:  like `SOCK_STREAM` but each all of [[li read]] will return a full message
- `SOCK_RAW`: raw network protocol access (only for [[li internet domain socket]])

#### [[stream communication]]
- sequenced
- reliable
- two-way full-duplex
- connection-based 
- asymetric ([[server]]/[[client]])
- e.g. [[transmission control protocol (TCP)]]

### [[datagram]]
- connectionless
- unreliable (package loss and out of order)
- fixed length packages
- symetric
- e.g. [[user datagram protocol (UDP)]]

Tags: code linux
<!--ID: 1708329969701-->
END




START
Basic
`SOCK_DGRAM` vs `SOCK_STREAM`
- concept differences
- setup differences
- usage differences

Back: 
#### [[stream communication]]
- sequenced
- reliable
- two-way full-duplex
- connection-based 
- asymetric ([[server]]/[[client]])
- e.g. [[transmission control protocol (TCP)]]

### [[datagram]]
- connectionless
- unreliable (package loss and out of order)
- fixed length packages
- symetric
- e.g. [[user datagram protocol (UDP)]]


### `SOCK_DGRAM`: [[li conection less socket]]
#### setup
- no connection has to be established like with a [[li connection based socket]] ([[li listen]], [[li connect]], [[li accept]] not needed)
1) [[server]] and [[client]] create a [[li socket]] with type `SOCK_DGRAM` and the same domain
2) the [[server]] binds an adress ([[IP]] or path) to the [[li socket]]


### communication between [[li conection less socket]]
- `SOCK_DGRAM` [[li conection less socket]] can use [[li sendto]] and [[li recvfrom]] to send or revic from a specific adress (ip or path)

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


### `SOCK_STREAM`: [[li connection based socket]]
### setup
#### establishing a connection
- to establish a [[li socket]] connection between a [[li socket]] on the [[server]] side and a [[li socket]] of the [[client]] side the following steps are done
- after this the [[li socket|sockets]] can communicate using the normal [[li file descriptor]] api ([[li read]], [[li write]])

1) both [[server]] and [[client]] create a [[li socket]] with a connection based type (`SOCK_STREAM` and `SOCK_SEQPACKET`)  using [[li socket]]
2) the [[server]] binds an adress ([[IP]] or path) to the [[li socket]] using [[li bind]]
3) the [[server]] marks the [[li socket]] as passiv (accepting of connection requests) using [[li listen]]
4) the [[client]] sends a connection request using the [[li connect]] [[li syscall]] 
5) the [[server]] creates new [[li socket]] that is connected to the [[client|clints]] [[li socket]] while the listing [[li socket]] keeps listing for connection requests using [[li accept]]

### communication 
#### send (syscall)
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

#### recv (syscall)
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





### [[li socket]]
- endpoint in a two-way communication channel
- for sending data between [[li process|processes]] either [[li unix domain socket|locally]] or over [[li internet domain socket|network]]
- can use the generic [[li file descriptor]] api ([[li read]], [[li write]]) but have a specific api that provides more options ([[li send]], [[li recv]], [[li sendto]], [[li recvfrom]])


#### type
- specifies communication semantics
- two different categorys that are avalibale for [[li unix domain socket]] and [[li internet domain socket]]
	- [[li connection based socket]]: `SOCK_STREAM`, `SOCK_SEQPACKET`
	- conection less: `SOCK_DGRAM`
- `SOCK_STREAM`: connection bases [[stream communication]] between a [[server]] and a [[client]]
- `SOCK_DGRAM`: [[datagram]] based connection less communication
- `SOCK_SEQPACKET`:  like `SOCK_STREAM` but each all of [[li read]] will return a full message
- `SOCK_RAW`: raw network protocol access (only for [[li internet domain socket]])



Tags: code linux
<!--ID: 1708606367198-->
END