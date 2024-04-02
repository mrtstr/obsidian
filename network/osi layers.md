![[application layer#application layer]]

![[session layer#session layer]]

![[transport layer#transport layer]]

![[network layer#network layer]]

![[data link layer#data link layer]]



![[transmission control protocol (TCP)#TCP connection and li socket]]


### [[li process]] to [[li process]] routing
- TCP demultiplexes incoming segments using (sender ip, sender port, reviever ip, reviever port) but cannot determine which [[li process]] gets an incoming segment 
- the operating system distributes the incomming [[transmission control protocol (TCP)#segement structure|segments]] to the [[li file descriptor]]/[[li socket]] based on the sender ([[internet protocol (IP)|IP adress]], [[port]]) 
	- if the sender of a connected [[li socket]] the socket gets the given segments
	- otherwise the [[li listen|listening]] [[li socket]] gets the segment 

### example: [[osi layers]] interaction

1) first a `SOCK_STREAM` `AF_INET` domain [[li socket]] connection has to be established
	1) [[client]] and [[server]] create a `SOCK_STREAM` `AF_INET` domain [[li socket]]
	2) the [[server]] uses the [[li bind]] [[li syscall]] to bind the socket to a [[port]] 
	3) the [[server]] uses the [[li listen]] [[li syscall]] make the socket listen to connection requests
	4)  the [[client]] uses the [[li connect]] [[li syscall]] to send a connection request to the [[internet protocol (IP)]]/[[port]] of the [[server]]
	5) the [[server]] uses the [[li accept]] [[li syscall]] to create a connected socket pair
2) [[transmission control protocol (TCP)|TCP connection]] establishment with a 3 way handshake
	1) the [[client]] sends a SYN with a radom initilized sequence number x
	2) the [[server]] responds with a SYN-ACK by sendeing a sement with a ACK number x+1 and his own randomly initilizes sequence number y
	3) the [[client]] confirms the sequence number of the server by acknolaging in with an ACK number of y+1
- each TCP segment is the payload of a [[internet protocol (IP)]] packet
- the [[internet protocol (IP)]] information is processed by the [[router]] and other [[networking devices]] while the [[transmission control protocol (TCP)]] sements are processes by the [[server]]/[[client]]
3) [[hypertext transfer protocol (HTTP)]] interaction
	1) a request is sent by the [[client]] to the [[server]]
	2) the [[server]] sends a response
	3) [[transmission control protocol (TCP)|TCP connection]] is closed or reused
4) [[transmission control protocol (TCP)|TCP connection]] might be closed with a 4 way handshake
5) [[li socket]] connection might be closed using the [[li close]] [[li syscall]]

# anki

START
Basic
network layers (5) 
- concept
- examples (4 + 1 + 2 + 1 + 3)
Back: 
### application layer
- high-level protocols for transfering
- [[hypertext transfer protocol (HTTP)]]
- [[secure shell protocol (SSH)]]
- [[domain name system (DNS)]]
- [[file transfer protocol (FTP)]]

### session layer
- managing communication session
- e.g. [[li socket]]

### transport layer
- transmission of data segments between points on a network
	→ acknowledgment, package segmentation
- concepts: [[stream communication]] ([[transmission control protocol (TCP)]]) or [[datagram]] ([[user datagram protocol (UDP)]])

### network layer
- Structuring and managing a multi-node network
	→  [[router|routing]]
- e.g. [[internet protocol (IP)]]

### data link layer
- phsical connection between nodes using e.g. data link [[switch|swiches]]
- makes sure the data get transmitted physicly to the right destination within a network
- works on [[media access code (MAC)]] level

Tags: code network
<!--ID: 1708703380412-->
END


START
Basic
TCP connection
- defintion 
- how is it identified?

Service endpoint vs [[li socket|TCP socket]]
- defintion 
- how are they identified?
- Difference

Back: 
### [[transmission control protocol (TCP)|TCP connection]] and [[li socket|sockets]] 
- [[transmission control protocol (TCP)|TCP]] connection is uniquely identified by its two service endpoints ([[internet protocol (IP)|IP adress]], [[port]]) 
	→ a TCP connection is identified by a 4-tuple (server ip, server port, client ip, client port)
- a [[li socket|AF_INTET domain SOCK_STEAM]] is a connection endpoint instance with an [[internet protocol (IP)|IP adress]] and a [[port]] (but not uniquely identified by them)
- a network service (address/port) can have multiple [[li socket|AF_INTET domain SOCK_STEAM]] but only one of them is [[li listen|listening]] to incomming connections requests
- appart from the [[li listen|listening]] [[li socket]] there can be multiple [[li socket|sockts]] that are connected to differen ip adresse/[[port]] combination but only one to each connection partner
- a TCP connection can be stablished after a `SOCK_STREAM` `AF_INET` domain stocket connection has been estabnished

#### [[li process]] to [[li process]] routing
- TCP demultiplexes incoming segments using (sender ip, sender port, reviever ip, reviever port) but cannot determine which [[li process]] gets an incoming segment 
- the operating system distributes the incomming [[transmission control protocol (TCP)#segement structure|segments]] to the [[li file descriptor]]/[[li socket]] based on the sender ([[internet protocol (IP)|IP adress]], [[port]]) 
	- if the sender of a connected [[li socket]] the socket gets the given segments
	- otherwise the [[li listen|listening]] [[li socket]] gets the segment 
Tags: code network
<!--ID: 1710614272487-->
END


START
Basic
- how does a TCP segment get sent from [[li process]] to [[li process]]?
- relationship between a [[li socket]] and [[internet protocol (IP)|IP adress]], [[port]] combination 
Back: 
### [[transmission control protocol (TCP)|TCP connection]] and [[li socket|sockets]] 
- [[transmission control protocol (TCP)|TCP]] connection is uniquely identified by its two service endpoints ([[internet protocol (IP)|IP adress]], [[port]]) 
	→ a TCP connection is identified by a 4-tuple (server ip, server port, client ip, client port)
- a [[li socket|AF_INTET domain SOCK_STEAM]] is a connection endpoint instance with an [[internet protocol (IP)|IP adress]] and a [[port]] (but not uniquely identified by them)
- a network service (address/port) can have multiple [[li socket|AF_INTET domain SOCK_STEAM]] but only one of them is [[li listen|listening]] to incomming connections requests
- appart from the [[li listen|listening]] [[li socket]] there can be multiple [[li socket|sockts]] that are connected to differen ip adresse/[[port]] combination but only one to each connection partner
- a TCP connection can be stablished after a `SOCK_STREAM` `AF_INET` domain stocket connection has been estabnished

#### [[li process]] to [[li process]] routing
- TCP demultiplexes incoming segments using (sender ip, sender port, reviever ip, reviever port) but cannot determine which [[li process]] gets an incoming segment 
- the operating system distributes the incomming [[transmission control protocol (TCP)#segement structure|segments]] to the [[li file descriptor]]/[[li socket]] based on the sender ([[internet protocol (IP)|IP adress]], [[port]]) 
	- if the sender of a connected [[li socket]] the socket gets the given segments
	- otherwise the [[li listen|listening]] [[li socket]] gets the segment 
Tags: code network
<!--ID: 1710614272489-->
END



START
Basic
how do the following concepts/protocols work togather?
- [[hypertext transfer protocol (HTTP)]]
- [[internet protocol (IP)]]
- [[transmission control protocol (TCP)]]
- [[li socket]]
5 steps: 5 + 3 + 3 + 1 + 1
Back: 

1) first a `SOCK_STREAM` `AF_INET` domain [[li socket]] connection has to be established
	1) [[client]] and [[server]] create a `SOCK_STREAM` `AF_INET` domain [[li socket]]
	2) the [[server]] uses the [[li bind]] [[li syscall]] to bind the socket to a [[port]] 
	3) the [[server]] uses the [[li listen]] [[li syscall]] make the socket listen to connection requests
	4)  the [[client]] uses the [[li connect]] [[li syscall]] to send a connection request to the [[internet protocol (IP)]]/[[port]] of the [[server]]
	5) the [[server]] uses the [[li accept]] [[li syscall]] to create a connected socket pair
2) [[transmission control protocol (TCP)|TCP connection]] establishment with a 3 way handshake
	1) the [[client]] sends a SYN with a radom initilized sequence number x
	2) the [[server]] responds with a SYN-ACK by sendeing a sement with a ACK number x+1 and his own randomly initilizes sequence number y
	3) the [[client]] confirms the sequence number of the server by acknolaging in with an ACK number of y+1
- each TCP segment is the payload of a [[internet protocol (IP)]] packet
- the [[internet protocol (IP)]] information is processed by the [[router]] and other [[networking devices]] while the [[transmission control protocol (TCP)]] sements are processes by the [[server]]/[[client]]
3) [[hypertext transfer protocol (HTTP)]] interaction
	1) a request is sent by the [[client]] to the [[server]]
	2) the [[server]] sends a response
	3) [[transmission control protocol (TCP)|TCP connection]] is closed or reused
4) [[transmission control protocol (TCP)|TCP connection]] might be closed with a 4 way handshake
5) [[li socket]] connection might be closed using the [[li close]] [[li syscall]]
____________________________

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
	- [[li conection less socket]]: `SOCK_DGRAM`
- `SOCK_STREAM`: connection bases [[stream communication]] between a [[server]] and a [[client]]
- `SOCK_DGRAM`: [[datagram]] based connection less communication

### [[transmission control protocol (TCP)]]
- [[statefulness of protocols|stateful]] [[protocol]] of the [[osi layers#transport layer|transport layer]] for [[stream communication|stream based]] data transfer
- managed by the operation system with a [[li connection based socket]]

#### [[stream communication]]
- **Byte-Oriented**: 
	- data treatet as a continuous stream of bytes
		→ no message boundaries, 
		→ the receiver must handle message framing
- **Ordered and Reliable**
	- Data delivery is guaranteed and in order
		→ If a packet is lost or corrupted, it will be retransmitted
- **Connection-Oriented**: 
	- connection between the sender and receiver has to be stablished before data transfer
- **Flow Control**: 
	- prevent sender from overwhelming the receiver
- e.g. [[transmission control protocol (TCP)]] used in [[li connection based socket]] (`SOCK_STREAM` and `SOCK_SEQPACKET`)


#### TCP connection and [[li socket]]
- [[transmission control protocol (TCP)|TCP]] connection is uniquely identified by its two service endpoints ([[internet protocol (IP)|IP adress]], [[port]]) 
	→ a TCP connection is identified by a 4-tuple (server ip, server port, client ip, client port)
- a [[li socket|AF_INTET domain SOCK_STEAM]] is a connection endpoint instance with an [[internet protocol (IP)|IP adress]] and a [[port]] (but not uniquely identified by them)
- a network service (address/port) can have multiple [[li socket|AF_INTET domain SOCK_STEAM]] but only one of them is [[li listen|listening]] to incomming connections requests
- appart from the [[li listen|listening]] [[li socket]] there can be multiple [[li socket|sockts]] that are connected to differen ip adresse/[[port]] combination but only one to each connection partner
- a TCP connection can be stablished after a `SOCK_STREAM` `AF_INET` domain stocket connection has been estabnished

### [[hypertext transfer protocol (HTTP)]]
-  simple and human-readable [[protocol]] in the [[application layer]] for transmitting data 
- interactions are bases on [[statefulness of protocols|stateless]] request/response pairs between a [[client]] and a [[server]]
-  extendable headers
- default [[port]] is TCP 80, but other ports can be used

### steps
1) establishement of [[transmission control protocol (TCP)|TCP connection]]
2) [[client]] sends a **request** to the [[server]]
3) [[server]] answers with a **response**
	- Request ([[client]] to [[server]])
	- Response ([[server]] to [[client]])
4) reusing or closing of [[transmission control protocol (TCP)|TCP connection]]

#### [[transmission control protocol (TCP)|TCP connection]] relationship
- first version one tcp connection per request response pair which is very inefficient
- later versions reusing of tcp connections for multiple request/response pairs
- **HTTP/1.0**: 
	- one connecterion per request/response pair
- **HTTP/1.1** 
	- TCP connection can be partially controlled using the connection header
- **HTTP/2** 
	- reusing of [[transmission control protocol (TCP)|tcp connections]] 
	- multiplexing messages over a single [[transmission control protocol (TCP)|tcp connection]]

Tags: code network
<!--ID: 1711910474758-->
END