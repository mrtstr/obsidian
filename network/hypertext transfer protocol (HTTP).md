## hypertext transfer protocol (HTTP)
-  simple and human-readable [[protocol]] in the [[application layer]] for transmitting data 
- interactions are bases on [[statefulness of protocols|stateless]] request/response pairs between a [[client]] and a [[server]]
-  extendable headers
- default [[port]] is TCP 80, but other ports can be used
- 

### steps
1) establishement of [[transmission control protocol (TCP)|TCP connection]]
2) [[client]] sends a **request** to the [[server]]
3) [[server]] answers with a **response**
	- Request ([[client]] to [[server]])
	- Response ([[server]] to [[client]])
4) reusing or closing of [[transmission control protocol (TCP)|TCP connection]]

### [[statefulness of protocols|statefulness]]
- [[hypertext transfer protocol (HTTP)]] is [[statefulness of protocols|stateless]]
- statefulness can be achived with HTTP cookies

![[statefulness of protocols#statefulness of protocols]]

### requirments for [[transport layer]] [[protocol]]
- reliable (which [[transmission control protocol (TCP)]] is but [[user datagram protocol (UDP)]] is not)
- does not need to be [[statefulness of protocols|stateful]] and connection based
	→ almost always used on top of [[transmission control protocol (TCP)]] 

### [[transmission control protocol (TCP)|TCP connection]] relationship
- first version one tcp connection per request response pair which is very inefficient
- later versions reusing of tcp connections for multiple request/response pairs
- **HTTP/1.0**: 
	- one connecterion per request/response pair
- **HTTP/1.1** 
	- TCP connection can be partially controlled using the connection header
- **HTTP/2** 
	- reusing of [[transmission control protocol (TCP)|tcp connections]] 
	- multiplexing messages over a single [[transmission control protocol (TCP)|tcp connection]]

![[transmission control protocol (TCP)#TCP connection]]



## packet structure
### header
- meta information
- document type
- encoding
### body
- transmitted data