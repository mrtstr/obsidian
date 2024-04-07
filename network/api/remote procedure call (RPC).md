## remote procedure call (RPC)
- architectural style (not a [[protocol]]) for designing distributed systems
- for executing non standarized subrutines on a remote system ([[server]]) by using a [[hypertext transfer protocol (HTTP)|POST request]] and the [[server]] will excure the specific function and return the resut with the response
	→ the [[client]] and [[server]] need to know the subroutines and how to use them
- can be used on every request response based [[protocol]] but ofen build on top of [[hypertext transfer protocol (HTTP)]]/[[transmission control protocol (TCP)]]
- multiple different implementation like [[gRPC]]


## [[remote procedure call (RPC)]] vs [[representational state transfer (REST) api]]

- REST: ressource centic
- RPC: verb centic

- REST: simple and standarized functions [[hypertext transfer protocol (HTTP)|HTTP verbs]] called by an intelligen caller on ressources
- RPC: intelligent non standarized functions that are known to [[client]] and [[server]] and are called with a [[hypertext transfer protocol (HTTP)|POST request]]

REST: 
- simpler 
- more stadardized
- higher degree of decupleing

RPC: 
- more powerful

# anki

START
Basic
 remote procedure call (RPC)
 - concept (5)
Back: 
#### remote procedure call (RPC)
- architectural style (not a [[protocol]]) for designing distributed systems
- for executing non standarized subrutines on a remote system ([[server]]) by using a [[hypertext transfer protocol (HTTP)|POST request]] and the [[server]] will excure the specific function and return the resut with the response
	→ the [[client]] and [[server]] need to know the subroutines and how to use them
- can be used on every request response based [[protocol]] but ofen build on top of [[hypertext transfer protocol (HTTP)]]/[[transmission control protocol (TCP)]]
- multiple different implementation like [[gRPC]]

Tags: code network
<!--ID: 1712504184372-->
END


START
Basic
 remote procedure call (RPC) vs [[representational state transfer (REST) api]]

Back: 
### [[remote procedure call (RPC)]] vs [[representational state transfer (REST) api]]

- REST: ressource centic
- RPC: verb centic

- REST: simple and standarized functions [[hypertext transfer protocol (HTTP)|HTTP verbs]] called by an intelligen caller on ressources
- RPC: intelligent non standarized functions that are known to [[client]] and [[server]] and are called with a [[hypertext transfer protocol (HTTP)|POST request]]

REST: 
- simpler 
- more stadardized
- higher degree of decupleing

RPC: 
- more powerful

### remote procedure call (RPC)
- architectural style (not a [[protocol]]) for designing distributed systems
- for executing non standarized subrutines on a remote system ([[server]]) by using a [[hypertext transfer protocol (HTTP)|POST request]] and the [[server]] will excure the specific function and return the resut with the response
	→ the [[client]] and [[server]] need to know the subroutines and how to use them
- can be used on every request response based [[protocol]] but ofen build on top of [[hypertext transfer protocol (HTTP)]]/[[transmission control protocol (TCP)]]
- multiple different implementation like [[gRPC]]

### representational state transfer (REST) api
- architectural style (not a [[protocol]]) for designing distributed systems
- mainly for performing standardized operations ([[hypertext transfer protocol (HTTP)|HTTP verbs]]) on ressources
- ressource centric
- the intelligence is on the [[client]] side while the [[server]] is only simple operations
- in principle [[protocol]] agnostic but in practive ofen build on top of [[hypertext transfer protocol (HTTP)]]/[[transmission control protocol (TCP)]]


#### principles
1) **[[client]]-[[server]] decupleing**: 
	- the [[server]] provides a service and the [[client]] can send a request
2) **[[statefulness of protocols|statelessness]]:**
	- the request contains all nessary information
	- the request is independent of requests before and after
3) **caching** is recommended
4) **uniform interface**
	- uniform adressing of ressrouces ([[uniform resource locator (URL)]])
	- flexible representation of ressources (e.g. one ressource can be delivered as [[json]], [[XML]] or [[HTML]])
	- standardized methods: e.g. [[hypertext transfer protocol (HTTP)#methods|HTTP verbs]]
5) **Layered System**
	- the system should be built in multiple layers hidden under a single interface
6) **Code on Demand** (optional) 
	- Servers are able to temporarily extend or customize the functionality of a client by transferring logic

Tags: code network
<!--ID: 1712504184378-->
END