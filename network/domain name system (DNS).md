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
how are [[uniform resource locator (URL)]] processed? (5 steps)

Back: 
1) [[network domain]] is extracted from the [[uniform resource locator (URL)]]
2) [[network domain]] is sent to a **domain name resolver** where It's either directly translated to an [[internet protocol (IP)]] adress of the server providing the ressource from the cache
3) if the requested [[network domain]] is not cached the request is forwarded to the **domain name server** that as the quthority over the top level domain
4) the request might be forwarded to **domain name servers** that have the authority over subdomains of the top level domain
5) when the [[network domain]] is tranlated to an [[internet protocol (IP)]] adress the specific ressource is requested (second pard of the URL) from the server

_______________________________
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

### uniform resource locator (URL)
- complete adress/location of a network ressource
- consists of two parts: 
	1) [[network domain]]
		- adress of the server that provides the ressource
		- dot seperated hirachical structure
		- translated by a [[domain name system (DNS)]] to a [[internet protocol (IP)]] adress if the server
		- e.g. `google.de`
	2) location of the ressource on the server: 
		- `/` seperated hiracical struture
		- processed by the server
		- e.g. `/impressum`

Tags: code network
<!--ID: 1711813346673-->
END