## [[domain name system (DNS)]]
- hierarchical and distributed naming system that translates
	- [[network domain]] to [[internet protocol (IP)]] adresses (forward lookup, more common)
	- [[internet protocol (IP)]] adresses to [[network domain]] (reverse lookup)
- happend on the [[application layer]] of the [[osi layers]]
- mapping is mainained by **domain name servers** that have the authority over a certain [[network domain|domain namespace]] 

### domain name servers
- has the authority over a [[network domain|domain]] name e.g. `.com`, `.de`, `.org`
- keeps track over the mapping between its known domain names and [[internet protocol (IP)]] adresses of the servers
- can give authority over a subdomain to another domain name server 
	- e.g. the authority over the subdomain of `google.de` has been given to google by the authority over `.de`

### domain name resolver
- processes queries
- responsable for
	- forwarding requests to the right **domain name servers** and 
	- caching the requests to reduce the traffic on the **domain name servers**


### DNS loadbalancing
- map a [[network domain]] to a group of [[internet protocol (IP)]] adresses
- DNS loadbalancing uses round-robin to decide with which up to answer the query
- there are move advanced methods for load balancing thus DNS load balancing is not that common anymore

_______________________________
![[network domain#network domain]]


# anki

START
Basic
[[domain name system (DNS)]]
- concept (3)
- parts (2: 3 + 2)

Back: 
## [[domain name system (DNS)]]
- hierarchical and distributed naming system that translates
	- [[network domain]] to [[internet protocol (IP)]] adresses (forward lookup, more common)
	- [[internet protocol (IP)]] adresses to [[network domain]] (reverse lookup)
- happend on the [[application layer]] of the [[osi layers]]
- mapping is mainained by **domain name servers** that have the authority over a certain [[network domain|domain namespace]] 

### domain name servers
- has the authority over a [[network domain|domain]] name e.g. `.com`, `.de`, `.org`
- keeps track over the mapping between its known domain names and [[internet protocol (IP)]] adresses of the servers
- can give authority over a subdomain to another domain name server 
	- e.g. the authority over the subdomain of `google.de` has been given to google by the authority over `.de`

### domain name resolver
- processes queries
- responsable for
	- forwarding requests to the right **domain name servers** and 
	- caching the requests to reduce the traffic on the **domain name servers**


### DNS loadbalancing
- map a [[network domain]] to a group of [[internet protocol (IP)]] adresses
- DNS loadbalancing uses round-robin to decide with which up to answer the query
- there are move advanced methods for load balancing thus DNS load balancing is not that common anymore

_______________________________

### [[network domain]]
- human-readable adress/name of a server
- can be translated to a [[internet protocol (IP)]] adress using a [[domain name system (DNS)]]
- hirachicaly devided into multiple levels of subdomains from right to left:
	- `<lowest level>.<mid level>.<top level domain>`
	- `en.google.de`

Tags: code network
<!--ID: 1711813346669-->
END


START
Basic
how are [[uniform resource identifier (URI)]] processed? (3 steps with details)

Back: 
#### resolve [[network domain]] to [[internet protocol (IP)|ip adress]] 
1) [[network domain]] is extracted from the [[uniform resource locator (URL)]]
2) [[network domain]] is sent to a **domain name resolver** where It's either directly translated to an [[internet protocol (IP)]] adress of the server providing the ressource from the cache
3) if the requested [[network domain]] is not cached the request is forwarded to the **domain name server** that as the quthority over the top level domain
4) the request might be forwarded to **domain name servers** that have the authority over subdomains of the top level domain

#### establish `SOCK_STREAM` [[li socket]] connection on [[port]] 
### establishing a connection
- to establish a [[li socket]] connection between a [[li socket]] on the [[server]] side and a [[li socket]] of the [[client]] side
- given that the [[server]] already has a [[li listen|listening]] `SOCK_STREAM` [[li socket]] on the [[port]] given in the [[uniform resource identifier (URI)]]

1) the [[client]] sends a connection request using the [[li connect]] [[li syscall]]
2) the [[server]] creates new [[li socket]] that is connected to the [[client|clints]] [[li socket]] while the listing [[li socket]] keeps listing for connection requests

#### calling [[hypertext transfer protocol (HTTP)|http]] method on ressource
- given that the [[transmission control protocol (TCP)]] has been established in the meantime
- [[hypertext transfer protocol (HTTP)]] 

_______________________________
## hypertext transfer protocol (HTTP)
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

### methods

#### GET
- request a ressource from a [[server]] with a [[uniform resource locator (URL)]]
- should only retrieve data and should not have any other effect
- all transmitted data are part of the [[uniform resource locator (URL)]]
- there can be a request body, but it will be ignored
- cachable
- idempotent

example request:
```
GET /infotext.html HTTP/1.1 # method path version
Host: www.example.net       # domain name
```

response example:
```
HTTP/1.1 200 OK    # version and status code
Server: Apache/1.3.29 (Unix) PHP/4.3.4  
Content-Length: 123456  
Content-Language: de
Connection: close
Content-Type: text/html
(request bode: html file)
```


### uniform resource identifier (URI)

- provide a way to access a ressource ([[uniform resource locator (URL)]])
- be a namespace
- be a **URN**: identifie a ressource but does not provide a way to access it

1) [[protocol]]: e.g. [[hypertext transfer protocol (HTTP)]]
2) [[port]]: e.g. 80
3) [[network domain]]
	- adress of the server that provides the ressource
	- dot seperated hirachical structure
	- translated by a [[domain name system (DNS)]] to a [[internet protocol (IP)]] adress if the server
	- e.g. `google.de`
4) path to a ressource
	- `/` seperated hiracical struture
	- processed by the server
	- e.g. `/impressum`
5) parameters (optional)
	- extra information provided to the [[server]] 
	- e.g. `?topic=ABC&name=XYZ`
6) ancor: specific part inside the ressource
	- e.g. `#sample`

### [[domain name system (DNS)]]
- hierarchical and distributed naming system that translates
	- [[network domain]] to [[internet protocol (IP)]] adresses (forward lookup, more common)
	- [[internet protocol (IP)]] adresses to [[network domain]] (reverse lookup)
- happend on the [[application layer]] of the [[osi layers]]
- mapping is mainained by **domain name servers** that have the authority over a certain [[network domain|domain namespace]] 

#### domain name servers
- has the authority over a [[network domain|domain]] name e.g. `.com`, `.de`, `.org`
- keeps track over the mapping between its known domain names and [[internet protocol (IP)]] adresses of the servers
- can give authority over a subdomain to another domain name server 
	- e.g. the authority over the subdomain of `google.de` has been given to google by the authority over `.de`

#### domain name resolver
- processes queries
- responsable for
	- forwarding requests to the right **domain name servers** and 
	- caching the requests to reduce the traffic on the **domain name servers**


### [[network domain]]
- human-readable adress/name of a server
- can be translated to a [[internet protocol (IP)]] adress using a [[domain name system (DNS)]]
- hirachicaly devided into multiple levels of subdomains from right to left:
	- `<lowest level>.<mid level>.<top level domain>`
	- `en.google.de`



Tags: code network
<!--ID: 1711813346673-->
END