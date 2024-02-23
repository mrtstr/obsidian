## [[li unix domain socket]]
- for bidirectional [[li interprocess communication]] inside a system
- can be bound to a path in the filesystem or unnamed
- usualy of type `SOCK_STREAM` but others are also possible
- behave like two [[li FIFO special file]] (one i each direction) or a to two [[li ordinary pipe]] (in case of unnamed sockets)

#### named [[li unix domain socket]]
- registed under a path in the filesystem
- than be opend to create [[li file descriptor]] to comunicate
- compariable to a bidirection [[li FIFO special file]]

#### unnamed [[li unix domain socket]]
- created as a pair in a already connected state unsing the [[li socketpair]] [[li syscall]]
- can only be used among the [[li child process]] of the [[li process]] that created them by passing the [[li file descriptor]]
- comparibale to a [[li ordinary pipe]]


![[stream_socket 1.jpg]]

### creating of [[li unix domain socket]]
1) a named [[li unix domain socket]] can be created, bound to a path in the local file system using [[li bind]] (see [[li FIFO special file]]) 
![[li socket (syscall)#socket (syscall)]]

![[li bind#bind (syscall)]]
2) unnamed (already connected) [[li unix domain socket]] can be created using the [[li socketpair]] [[li syscall]] and passed to the [[li child process]] (see [[li ordinary pipe]])
![[li socketpair#socketpair (syscall)]]



![[li socket#li socket]]


# anki

START
Basic
[[li unix domain socket]]
- concept
- how it is created (2 different kinds)

Back: 
### [[li unix domain socket]]
- for bidirectional [[li interprocess communication]] inside a system
- can be bound to a path in the filesystem or unnamed
- usualy of type `SOCK_STREAM` but others are also possible
- implementet with two buffers (one for each direction)
	→ compariable to two [[li ordinary pipe]] (in case of unnamed sockets) or [[li FIFO special file]] (when the [[li unix domain socket]] is bound to the file system

![[stream_socket 2.jpg]]
#### named [[li unix domain socket]]
- registed under a path in the filesystem
- than be opend to create [[li file descriptor]] to comunicate
- compariable to a bidirection [[li FIFO special file]]

#### unnamed [[li unix domain socket]]
- created as a pair in a already connected state unsing the [[li socketpair]] [[li syscall]]
- can only be used among the [[li child process]] of the [[li process]] that created them by passing the [[li file descriptor]]
- comparibale to a [[li ordinary pipe]]

#### creating of [[li unix domain socket]]
1) a named [[li unix domain socket]] can be created, bound to a path in the local file system using [[li bind]] (see [[li FIFO special file]]) 

### socket (syscall)
- [[li syscall]] for creating an [[li socket]] endpoint 
- returns a [[li file descriptor]] that refers to that endpoint
```C
socket(
	domain,  
	type, 
) // → file descriptor
```

#### bind (syscall)
- [[li syscall]] for binding an adress to and existing [[li socket]]
- while the [[server]] uses [[li bind]] to bind a adress to a [[li socket]] the [[client]] uses [[li connect]] to connect to the adress
- [[li unix domain socket]]: the adress is a filesystem path
- [[li internet domain socket]]: adress is a [[internet protocol (IP)]] adress
```C
int bind(
	sockfd, // file descriptor for the socket
	sockadd, // adress (path or ip) to bind to the file descriptor
) // -> return code
```

2) unnamed (already connected) [[li unix domain socket]] can be created using the [[li socketpair]] [[li syscall]] and passed to the [[li child process]] (see [[li ordinary pipe]])
3) 
#### socketpair (syscall)
- [[li syscall]] for creating an already connected pair of [[li unix domain socket]]
- for communincating among [[li child process]] similar to bidirectional version of a [[li ordinary pipe]] 
- writes the two [[li file descriptor]] in `sv[0]` and `sv[1]` and returns a [[li return code]]
```C
int socketpair(
	domain,  
	type, 
	sv[2],
) // → return code
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
	- [[li connection based socket]]: `SOCK_STREAM`, `SOCK_SEQPACKET`
	- conection less: `SOCK_DGRAM`
- `SOCK_STREAM`: connection bases [[stream communication]] between a [[server]] and a [[client]]
- `SOCK_DGRAM`: [[datagram]] based connection less communication
- `SOCK_SEQPACKET`:  like `SOCK_STREAM` but each all of [[li read]] will return a full message
- `SOCK_RAW`: raw network protocol access (only for [[li internet domain socket]])

Tags: code linux
<!--ID: 1708606367190-->
END



START
Basic
[[li unix domain socket]]
- named vs unnamed

Back: 
#### named [[li unix domain socket]]
- registed under a path in the filesystem
- than be opend to create [[li file descriptor]] to comunicate
- compariable to a bidirection [[li FIFO special file]]
- can be created and bound to a path in the local file system using [[li bind]] (see [[li FIFO special file]]) 

#### socket (syscall)
- [[li syscall]] for creating an [[li socket]] endpoint 
- returns a [[li file descriptor]] that refers to that endpoint
```C
socket(
	domain,  
	type, 
) // → file descriptor
```

#### bind (syscall)
- [[li syscall]] for binding an adress to and existing [[li socket]]
- while the [[server]] uses [[li bind]] to bind a adress to a [[li socket]] the [[client]] uses [[li connect]] to connect to the adress
- [[li unix domain socket]]: the adress is a filesystem path
- [[li internet domain socket]]: adress is a [[internet protocol (IP)]] adress
```C
int bind(
	sockfd, // file descriptor for the socket
	sockadd, // adress (path or ip) to bind to the file descriptor
) // -> return code
```

#### unnamed [[li unix domain socket]]
- created as a pair in a already connected state unsing the [[li socketpair]] [[li syscall]]
- comparibale to a [[li ordinary pipe]]

#### socketpair (syscall)
- [[li syscall]] for creating an already connected pair of [[li unix domain socket]]
- for communincating among [[li child process]] similar to bidirectional version of a [[li ordinary pipe]] 
- writes the two [[li file descriptor]] in `sv[0]` and `sv[1]` and returns a [[li return code]]
```C
int socketpair(
	domain,  
	type, 
	sv[2],
) // → return code
```

### [[li unix domain socket]]
- for bidirectional [[li interprocess communication]] inside a system
- can be bound to a path in the filesystem or unnamed
- usualy of type `SOCK_STREAM` but others are also possible
- implementet with two buffers (one for each direction)
	→ compariable to two [[li ordinary pipe]] (in case of unnamed sockets) or [[li FIFO special file]] (when the [[li unix domain socket]] is bound to the file system


Tags: code linux
<!--ID: 1708606367195-->
END



