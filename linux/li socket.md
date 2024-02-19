## [[li socket]]
- endpoint in a two-way communication channel
- for sending data between [[li process|processes]] either [[li unix domain socket|locally]] or over [[li network socket|network]]

### domain
- selects the protocol family which will be used for communication
	- `AF_UNIX` for [[li unix domain socket]] (like a local [[li file]])
	- `AF_INET`/`AF_INET6`: for [[li network socket]] using the [[IP]] protocol

### type
- specifies communication semantics
- `SOCK_STREAM`
	- [[stream communication]] (byte [[stream]]) based
		- sequenced
		- reliable
		- two-way full-duplex
		- connection-based 
- `SOCK_DGRAM`: 
	- [[datagram]] (package) based communication
		- connectionless
		- unreliable (package loss and out of order)
		- fixed length packages
- `SOCK_SEQPACKET`
	- like `SOCK_STREAM` but each all of [[li read]] will return a full message
- `SOCK_RAW` 
	- raw network protocol access
	- direct control over the communications and its packets

## [[li syscall]]
- can be created using the [[li socket]] [[li syscall]] and is used like a normal [[li file descriptor]] with [[li write]], [[li read]], [[li close]]
- a [[li socket]] can be bould to an adress using the [[li bind]] [[li syscall]] 
	- [[li unix domain socket]]: bind to a path in the filesystem
	- [[li network socket]]: bind to a network/[[IP]] adress
- the [[li syscall]] `send` and `recv` can be used instead of [[li read]] and [[li write]] but they are more or less equivalent

![[li socket (syscall)#socket (syscall)]]

![[li close#li close]]


![[li connect#li connect (syscall)]]

![[li bind#bind (syscall)]]


![[li write#write (syscall)]]

![[li read#read (syscall)]]



# anki

START
Basic
[[li socket]]
- concept
- domain (2)
- types (4)
- [[li syscall]] (6)

Back: 
## [[li socket]]
- endpoint in a two-way communication channel
- for sending data between [[li process|processes]] either [[li unix domain socket|locally]] or over [[li network socket|network]]

### domain
- selects the protocol family which will be used for communication
	- `AF_UNIX` for [[li unix domain socket]] (like a local [[li file]])
	- `AF_INET`/`AF_INET6`: for [[li network socket]] using the [[IP]] protocol

### type
- specifies communication semantics
- `SOCK_STREAM`
	- [[stream communication]] (byte [[stream]]) based
		- sequenced
		- reliable
		- two-way full-duplex
		- connection-based 
- `SOCK_DGRAM`: 
	- [[datagram]] (package) based communication
		- connectionless
		- unreliable (package loss and out of order)
		- fixed length packages
- `SOCK_SEQPACKET`
	- like `SOCK_STREAM` but each all of [[li read]] will return a full message
- `SOCK_RAW` 
	- raw network protocol access
	- direct control over the communications and its packets

## [[li syscall]]
- can be created using the [[li socket]] [[li syscall]] and is used like a normal [[li file descriptor]] with [[li write]], [[li read]], [[li close]]
- a [[li socket]] can be bould to an adress using the [[li bind]] [[li syscall]] 
	- [[li unix domain socket]]: bind to a path in the filesystem
	- [[li network socket]]: bind to a network/[[IP]] adress
- the [[li syscall]] `send` and `recv` can be used instead of [[li read]] and [[li write]] but they are more or less equivalent

### socket (syscall)
- [[li syscall]] for creating an [[li socket]] endpoint 
- returns a [[li file descriptor]] that refers to that endpoint
```C
socket(
	domain,  
	type, 
) // → file descriptor
```

### [[li close]]
- [[li syscall]] for closing a [[li file descriptor]]


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

### bind (syscall)
- [[li syscall]] for binding an adress to and existing [[li socket]]
- while the [[server]] uses [[li bind]] to bind a adress to a [[li socket]] the [[client]] uses [[li connect]] to connect to the adress
- in case of a [[li unix domain socket]] [[li bind]] can be used to bind the socket to a  filesystem path
```C
bind(
	sockfd, // file descriptor for the socket
	sockadd, // adress to bind to the file descriptor
) // -> return code
```


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

Tags: code linux
<!--ID: 1708329969701-->
END