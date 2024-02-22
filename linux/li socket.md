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



