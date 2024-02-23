## [[li internet domain socket]]
- for bidirectional [[li interprocess communication]] over the network
- domain `AF_INET` or `AF_INET6` depending on which version of [[internet protocol (IP)]] is used
- [[li connection based socket]]: using the [[transmission control protocol (TCP)]]
- [[li conection less socket]]: using the [[user datagram protocol (UDP)]]



# anki


START
Basic
[[li unix domain socket]] vs [[li internet domain socket]]

Back: 

### [[li unix domain socket]]
- for bidirectional [[li interprocess communication]] inside a system
- can be bound to a path in the filesystem or unnamed
- usualy of type `SOCK_STREAM` but others are also possible
- implementet with two buffers (one for each direction)
	→ compariable to two [[li ordinary pipe]] (in case of unnamed sockets) or [[li FIFO special file]] (when the [[li unix domain socket]] is bound to the file system

### [[li internet domain socket]]
- for bidirectional [[li interprocess communication]] over the network
- domain `AF_INET` or `AF_INET6` depending on which version of [[internet protocol (IP)]] is used
- [[li connection based socket]]: using the [[transmission control protocol (TCP)]]
- [[li conection less socket]]: using the [[user datagram protocol (UDP)]]

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
<!--ID: 1708611033509-->
END