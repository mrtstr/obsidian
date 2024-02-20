## [[li socket]]
- endpoint in a two-way communication channel
- for sending data between [[li process|processes]] either [[li unix domain socket|locally]] or over [[li internet domain socket|network]]

### domain
- selects the protocol family which will be used for communication
	- `AF_UNIX` for [[li unix domain socket]] (like a local [[li file]])
	- `AF_INET`/`AF_INET6`: for [[li internet domain socket]] using the [[IP]] protocol

![[1 ekw1o4xE_7ew9kYh6tVkCA.webp]]

### type
- specifies communication semantics
- two different categorys that are avalibale for [[li unix domain socket]] and [[li internet domain socket]]
	- connection based: `SOCK_STREAM`, `SOCK_SEQPACKET`
	- conection less: `SOCK_DGRAM`
- `SOCK_STREAM`: connection bases [[stream communication]] between a [[server]] and a [[client]]
- `SOCK_DGRAM`: [[datagram]] based connection less communication
- `SOCK_SEQPACKET`:  like `SOCK_STREAM` but each all of [[li read]] will return a full message
- `SOCK_RAW`: raw network protocol access (only for [[li internet domain socket]])

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

![[socket_connection.webp]]

![[dgram_sock_connectionless.gif]]


## [[li syscall]]
- can be created using the [[li socket]] [[li syscall]] and is used like a normal [[li file descriptor]] with [[li write]], [[li read]], [[li close]]
- a [[li socket]] can be bould to an adress using the [[li bind]] [[li syscall]] 
	- [[li unix domain socket]]: bind to a path in the filesystem
	- [[li internet domain socket]]: bind to a network/[[IP]] adress
- the [[li syscall]] `send` and `recv` can be used instead of [[li read]] and [[li write]] but they are more or less equivalent






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

### domain
- selects the protocol family which will be used for communication
	- `AF_UNIX` for [[li unix domain socket]] (like a local [[li file]])
	- `AF_INET`/`AF_INET6`: for [[li internet domain socket]] using the [[IP]] protocol

![[1 ekw1o4xE_7ew9kYh6tVkCA 1.webp]]


### type
- specifies communication semantics
- two different categorys that are avalibale for [[li unix domain socket]] and [[li internet domain socket]]
	- connection based: `SOCK_STREAM`, `SOCK_SEQPACKET`
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
- conecpt connection based [[li socket|sockets]]
- steps for establishing a connection between connection based [[li socket|sockets]]
Back: 
## connection based [[li socket|sockets]]
- [[li socket|socket types]] `SOCK_STREAM` and `SOCK_SEQPACKET`
- connection has to be established first
- can be [[li unix domain socket]] or [[li internet domain socket]]

![[1 3Ny5SBf14TwhpRR5vOqF2A 1.webp]]

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


![[socket_connection 1.webp]]
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

#### domain
- selects the protocol family which will be used for communication
	- `AF_UNIX` for [[li unix domain socket]] (like a local [[li file]])
	- `AF_INET`/`AF_INET6`: for [[li internet domain socket]] using the [[IP]] protocol

#### type
- specifies communication semantics
- two different categorys that are avalibale for [[li unix domain socket]] and [[li internet domain socket]]
	- connection based: `SOCK_STREAM`, `SOCK_SEQPACKET`
	- conection less: `SOCK_DGRAM`
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

#### domain
- selects the protocol family which will be used for communication
	- `AF_UNIX` for [[li unix domain socket]] (like a local [[li file]])
	- `AF_INET`/`AF_INET6`: for [[li internet domain socket]] using the [[IP]] protocol

#### type
- specifies communication semantics
- two different categorys that are avalibale for [[li unix domain socket]] and [[li internet domain socket]]
	- connection based: `SOCK_STREAM`, `SOCK_SEQPACKET`
	- conection less: `SOCK_DGRAM`
- `SOCK_STREAM`: connection bases [[stream communication]] between a [[server]] and a [[client]]
- `SOCK_DGRAM`: [[datagram]] based connection less communication
- `SOCK_SEQPACKET`:  like `SOCK_STREAM` but each all of [[li read]] will return a full message
- `SOCK_RAW`: raw network protocol access (only for [[li internet domain socket]])
Tags: code linux
<!--ID: 1708430646477-->
END