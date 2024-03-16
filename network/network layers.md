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
	→ [[adressing]], [[routing]], [[network traffic control]]
- e.g. [[internet protocol (IP)]]


## [[li socket|TCP connections]] and [[li socket|sockets]] 
### definitions
- TCP connection is defined by two service endpoints ([[internet protocol (IP)|IP adress]], [[port]]) 
	→ a TCP connection is identified by a 4-tuple (server ip, server port, client ip, client port)
- a [[li socket|TCP socket]] is a connection endpoint instance with an [[internet protocol (IP)|IP adress]] and a [[port]] (but not uniquely identified by them)
- a network service (address/port) can have multiple sockets but only one of them is [[li listen|listening]] to incomming connections requests
- appart from the [[li listen|listening]] [[li socket]] there can be multiple [[li socket|sockts]] that are connected

### [[li process]] to [[li process]] routing
- TCP demultiplexes incoming segments using (sender ip, sender port, reviever ip, reviever port) but cannot determine which [[li process]] gets an incoming segment 
- the operating system distributes the incomming [[transmission control protocol (TCP)#segement structure|segments]] to the [[li file descriptor]]/[[li socket]] based on the sender ([[internet protocol (IP)|IP adress]], [[port]]) 
	- if the sender of a connected [[li socket]] the socket gets the given segments
	- otherwise the [[li listen|listening]] [[li socket]] gets the segment 

# anki

START
Basic
network layers (4) 
- concept
- examples (4 + 1 + 2 + 1)
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
	→ [[adressing]], [[routing]], [[network traffic control]]
- e.g. [[internet protocol (IP)]]
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
### [[li socket|TCP connections]] and [[li socket|sockets]] 
#### definitions
- TCP connection is defined by two service endpoints ([[internet protocol (IP)|IP adress]], [[port]]) 
	→ a TCP connection is identified by a 4-tuple (server ip, server port, client ip, client port)
- a [[li socket|TCP socket]] is a connection endpoint instance with an [[internet protocol (IP)|IP adress]] and a [[port]] (but not uniquely identified by them)
- a network service (address/port) can have multiple sockets but only one of them is [[li listen|listening]] to incomming connections requests
- appart from the [[li listen|listening]] [[li socket]] there can be multiple [[li socket|sockts]] that are connected

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
### [[li socket|TCP connections]] and [[li socket|sockets]] 
#### definitions
- TCP connection is defined by two service endpoints ([[internet protocol (IP)|IP adress]], [[port]]) 
	→ a TCP connection is identified by a 4-tuple (server ip, server port, client ip, client port)
- a [[li socket|TCP socket]] is a connection endpoint instance with an [[internet protocol (IP)|IP adress]] and a [[port]] (but not uniquely identified by them)
- a network service (address/port) can have multiple sockets but only one of them is [[li listen|listening]] to incomming connections requests
- appart from the [[li listen|listening]] [[li socket]] there can be multiple [[li socket|sockts]] that are connected

#### [[li process]] to [[li process]] routing
- TCP demultiplexes incoming segments using (sender ip, sender port, reviever ip, reviever port) but cannot determine which [[li process]] gets an incoming segment 
- the operating system distributes the incomming [[transmission control protocol (TCP)#segement structure|segments]] to the [[li file descriptor]]/[[li socket]] based on the sender ([[internet protocol (IP)|IP adress]], [[port]]) 
	- if the sender of a connected [[li socket]] the socket gets the given segments
	- otherwise the [[li listen|listening]] [[li socket]] gets the segment 
Tags: code network
<!--ID: 1710614272489-->
END