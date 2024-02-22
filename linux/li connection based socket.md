## connection based [[li socket|sockets]]
- [[li socket|socket types]] `SOCK_STREAM` and `SOCK_SEQPACKET`
- connection has to be established first
- can be [[li unix domain socket]] or [[li internet domain socket]]

![[1 3Ny5SBf14TwhpRR5vOqF2A.webp]]

![[stream communication#stream communication]]

### establishing a connection
- to establish a [[li socket]] connection between a [[li socket]] on the [[server]] side and a [[li socket]] of the [[client]] side the following steps are done
- after this the [[li socket|sockets]] can communicate using the normal [[li file descriptor]] api ([[li read]], [[li write]])

1) both [[server]] and [[client]] create a [[li socket]] with a connection based type (`SOCK_STREAM` and `SOCK_SEQPACKET`) 
![[li socket (syscall)#socket (syscall)]]

2) the [[server]] binds an adress ([[IP]] or path) to the [[li socket]]
![[li bind#bind (syscall)]]

3) the [[server]] marks the [[li socket]] as passiv (accepting of connection requests)

![[li listen#listen (syscall)]]

4) the [[client]] sends a connection request using the [[li connect]] [[li syscall]]

![[li connect#li connect (syscall)]]

5) the [[server]] creates new [[li socket]] that is connected to the [[client|clints]] [[li socket]] while the listing [[li socket]] keeps listing for connection requests

![[li accept#accept (syscall)]]

![[socket_connection 1.jpg]]


### communication between connected [[li connection based socket]]
- the generic [[li file descriptor]] api ([[li write]], [[li read]]) can be used 
![[li write#write (syscall)]]

![[li read#read (syscall)]]
- there is also an api specific for connected [[li connection based socket]] for sending [[li send]] and reciving [[li recv]] data that provides more options (see `flags`)
- specific api [[li send]] for connected [[li connection based socket]] [[li send]] 

![[li send#send (syscall)]]

![[li recv#recv (syscall)]]
- there is also a lower level api that transfers message structs and can provide more flexibilty: [[li sendto]], [[li recvfrom]]
- [[li send]] and [[li recv]] are just a wrapper around the userlaying [[li sendmsg]] and [[li recvmsg]]

![[li sendmsg#sendmsg (syscall)]]

![[li recvmsg#recvmsg (syscall)]]

- the [[li sendto]] and [[li recvfrom]] api for [[li conection less socket]] can also be used but does not make sense because the destination adress would just be irgnored which maked it equivalent to [[li send]]/[[li recv]]

# anki

START
Basic
- conecpt connection based [[li socket|sockets]]
- communication between connected [[li connection based socket]]
	- [[li syscall]] (4) with arguments
Back: 
### connection based [[li socket|sockets]]
- [[li socket|socket types]] `SOCK_STREAM` and `SOCK_SEQPACKET`
- connection has to be established first
- can be [[li unix domain socket]] or [[li internet domain socket]]



### communication between connected [[li connection based socket]]
- the generic [[li file descriptor]] api ([[li write]], [[li read]]) can be used 
### write (syscall)
- [[li syscall]] for writing `count` bytes to a [[li file descriptor]] from the [[li virtual memory]] starting at adress `buff`
```C
int write(
	count, // number of bytes
	buff,  // vm adress of data to write
)
```

### read (syscall)
- [[li syscall]] for reading `count` bytes from a [[li file descriptor]] and writing it to the [[li virtual memory]] starting at adress `buff`
```C
int read(
	count, 
	buff,
) // -> return code
```

- there is also an api specific for connected [[li connection based socket]] for sending [[li send]] and reciving [[li recv]] data that provides more options (see `flags`)
- specific api [[li send]] for connected [[li connection based socket]] [[li send]] 

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

- there is also a lower level api that transfers message structs and can provide more flexibilty: [[li sendto]], [[li recvfrom]]
- [[li send]] and [[li recv]] are just a wrapper around the userlaying [[li sendmsg]] and [[li recvmsg]]

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

- the [[li sendto]] and [[li recvfrom]] api for [[li conection less socket]] can also be used but does not make sense because the destination adress would just be irgnored which maked it equivalent to [[li send]]/[[li recv]]

### [[stream communication]]
- sequenced
- reliable
- two-way full-duplex
- connection-based 
- asymetric ([[server]]/[[client]])
- e.g. [[transmission control protocol (TCP)]]


### [[li socket]]
- endpoint in a two-way communication channel
- for sending data between [[li process|processes]] either [[li unix domain socket|locally]] or over [[li internet domain socket|network]]
- can use the generic [[li file descriptor]] api ([[li read]], [[li write]]) but have a specific api that provides more options ([[li send]], [[li recv]], [[li sendto]], [[li recvfrom]])

#### domain
- selects the protocol family which will be used for communication
	- `AF_UNIX` for [[li unix domain socket]] (like a local [[li file]])
	- `AF_INET`/`AF_INET6`: for [[li internet domain socket]] using the [[IP]] protocol

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
<!--ID: 1708600002640-->
END





START
Basic
- conecpt connection based [[li socket|sockets]]
- steps for establishing a connection between connection based [[li socket|sockets]]
Back: 
## connection based [[li socket|sockets]]
- [[li socket|socket types]] `SOCK_STREAM` and `SOCK_SEQPACKET`
- connection has to be established first
- can be [[li unix domain socket]] or [[li internet domain socket]]

![[stream_socket.jpg]]

#### [[stream communication]]
- sequenced
- reliable
- two-way full-duplex
- connection-based 
- asymetric ([[server]]/[[client]])
- e.g. [[transmission control protocol (TCP)]]

### establishing a connection
- to establish a [[li socket]] connection between a [[li socket]] on the [[server]] side and a [[li socket]] of the [[client]] side the following steps are done
- after this the [[li socket|sockets]] can communicate using the normal [[li file descriptor]] api ([[li read]], [[li write]])

1) both [[server]] and [[client]] create a [[li socket]] with a connection based type (`SOCK_STREAM` and `SOCK_SEQPACKET`) 

### socket (syscall)
- [[li syscall]] for creating an [[li socket]] endpoint 
- returns a [[li file descriptor]] that refers to that endpoint
```C
socket(
	domain,  
	type, 
) // → file descriptor
```

2) the [[server]] binds an adress ([[IP]] or path) to the [[li socket]]
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

3) the [[server]] marks the [[li socket]] as passiv (accepting of connection requests)

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

4) the [[client]] sends a connection request using the [[li connect]] [[li syscall]]

### li connect (syscall)
- [[li syscall]] for initiating a connection on an existing [[li socket]]
- if the [[li socket]] type is `SOCK_DGRAM` the adress will be the default adress to send to and the only adress to reciev from but no conenction is created immediately
- if the [[li socket]] type is `SOCK_STREAM` the connection to the address will be created immediately
```C
connect(
	sockfd, // file descriptor for the socket
	sockadd, // adress to connect to *
) // -> return code
```

5) the [[server]] creates new [[li socket]] that is connected to the [[client|clints]] [[li socket]] while the listing [[li socket]] keeps listing for connection requests

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

![[socket_connection.jpg]]

### [[li socket]]
- endpoint in a two-way communication channel
- for sending data between [[li process|processes]] either [[li unix domain socket|locally]] or over [[li internet domain socket|network]]
- can use the generic [[li file descriptor]] api ([[li read]], [[li write]]) but have a specific api that provides more options ([[li send]], [[li recv]], [[li sendto]], [[li recvfrom]])

#### domain
- selects the protocol family which will be used for communication
	- `AF_UNIX` for [[li unix domain socket]] (like a local [[li file]])
	- `AF_INET`/`AF_INET6`: for [[li internet domain socket]] using the [[IP]] protocol

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
<!--ID: 1708430646471-->
END


START
Basic
how to create a [[li socket]] that is listing to connection requests under a certain adress (server side)
- [[li syscall]] with parameters and return value
Back: 
1) create a [[li socket]] connection based [[li socket]] (`SOCK_STREAM`, `SOCK_SEQPACKET`) using [[li socket]] ([[li unix domain socket]] or [[li internet domain socket]])
2) [[li bind]] an adress to the [[li socket]]
3) turn the [[li socket]] in listing mode using [[li listen]]

### socket (syscall)
- [[li syscall]] for creating an [[li socket]] endpoint 
- returns a [[li file descriptor]] that refers to that endpoint
```C
socket(
	domain,  
	type, 
) // → file descriptor
```

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

### [[li socket]]
- endpoint in a two-way communication channel
- for sending data between [[li process|processes]] either [[li unix domain socket|locally]] or over [[li internet domain socket|network]]
- can use the generic [[li file descriptor]] api ([[li read]], [[li write]]) but have a specific api that provides more options ([[li send]], [[li recv]], [[li sendto]], [[li recvfrom]])

#### domain
- selects the protocol family which will be used for communication
	- `AF_UNIX` for [[li unix domain socket]] (like a local [[li file]])
	- `AF_INET`/`AF_INET6`: for [[li internet domain socket]] using the [[IP]] protocol

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
<!--ID: 1708430646474-->
END



START
Basic
how to establish a connection between a listening [[li socket]] on the [[server]] side and a [[li socket]] on the [[client]]
- [[li syscall]] with parameters and return value
- summary of steps before that
Back: 
given both [[client]] and [[server]] have created a [[li socket]] of type `SOCK_STREAM` or `SOCK_SEQPACKET` and the socker of the server is bound to a known adress and is listing

1) the [[client]] sends a connection request using the [[li connect]] [[li syscall]]
2) the [[server]] creates new [[li socket]] that is connected to the [[client|clints]] [[li socket]] while the listing [[li socket]] keeps listing for connection requests using [[li accept]]

#### li connect (syscall)
- [[li syscall]] for initiating a connection on an existing [[li socket]]
- if the [[li socket]] type is `SOCK_DGRAM` the adress will be the default adress to send to and the only adress to reciev from but no conenction is created immediately
- if the [[li socket]] type is `SOCK_STREAM` the connection to the address will be created immediately
```C
connect(
	sockfd, // file descriptor for the socket
	sockadd, // adress to connect to *
) // -> return code
```

#### accept (syscall)
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


### nesseary steps before
1) [[li socket]]
2) [[li bind]]
3) [[li listen]]
### socket (syscall)
- [[li syscall]] for creating an [[li socket]] endpoint 
- returns a [[li file descriptor]] that refers to that endpoint
```C
socket(
	domain,  
	type, 
) // → file descriptor
```

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

### [[li socket]]
- endpoint in a two-way communication channel
- for sending data between [[li process|processes]] either [[li unix domain socket|locally]] or over [[li internet domain socket|network]]
- can use the generic [[li file descriptor]] api ([[li read]], [[li write]]) but have a specific api that provides more options ([[li send]], [[li recv]], [[li sendto]], [[li recvfrom]])

#### domain
- selects the protocol family which will be used for communication
	- `AF_UNIX` for [[li unix domain socket]] (like a local [[li file]])
	- `AF_INET`/`AF_INET6`: for [[li internet domain socket]] using the [[IP]] protocol

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
<!--ID: 1708430646477-->
END