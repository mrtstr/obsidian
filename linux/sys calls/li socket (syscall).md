### socket (syscall)
- [[li syscall]] for creating an [[li socket]] endpoint 
- returns a [[li file descriptor]] that refers to that endpoint
```C
socket(
	domain,  
	type, 
) // → file descriptor
```

# relevant
![[li socket#li socket]]

# anki
START
Basic
how to create a [[li socket]] (2)
- [[li syscall]] with parameters and return value
- different kinds (2 * 4)
Back: 
### socket (syscall)
- [[li syscall]] for creating an [[li socket]] endpoint 
- returns a [[li file descriptor]] that refers to that endpoint
```C
socket(
	domain,  
	type, 
) // → file descriptor
```

### socketpair (syscall)
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

#### domain
- selects the protocol family which will be used for communication
	- `AF_UNIX` for [[li unix domain socket]] (like a local [[li file]])
	- `AF_INET`/`AF_INET6`: for [[li internet domain socket]] using the [[internet protocol (IP)]] protocol

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
<!--ID: 1708430646462-->
END