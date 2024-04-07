## representational state transfer (REST) api
- architectural style (not a [[protocol]]) for designing distributed systems
- mainly for performing standardized operations ([[hypertext transfer protocol (HTTP)|HTTP verbs]]) on ressources
- ressource centric
- the intelligence is on the [[client]] side while the [[server]] is only simple operations
- in principle [[protocol]] agnostic but in practive ofen build on top of [[hypertext transfer protocol (HTTP)]]/[[transmission control protocol (TCP)]]


### principles
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

# anki

START
Basic
representational state transfer (REST) api
- concept (4)
- principles (6)
- relationship to [[protocol]]
Back: 
## representational state transfer (REST) api
- architectural style (not a [[protocol]]) for designing distributed systems
- mainly for performing standardized operations ([[hypertext transfer protocol (HTTP)|HTTP verbs]]) on ressources
- ressource centric
- the intelligence is on the [[client]] side while the [[server]] is only simple operations
- in principle [[protocol]] agnostic but in practive ofen build on top of [[hypertext transfer protocol (HTTP)]]/[[transmission control protocol (TCP)]]


### principles
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
<!--ID: 1712485036098-->
END