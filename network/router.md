## router
### definition
- A [[ip network|networking]] device that connects multiple [[ip network|networks]] together and forwards data packets between them
	→ selecting paths for data packets to cross [[ip network|networks]] 
- if the destination of a package is within another [[subnetwork]] the router will send it to the [[router]] of the desination [[subnetwork]]
- within the network [[switch|swiches]] are used to distribute the packages (most [[router|routers]] have swiches included and thus have multiple [[ethernet]] ports)
- works on the [[network layers|network layer]] using the [[internet protocol (IP)]] adress

### routing table
- is a [data table](https://en.wikipedia.org/wiki/Data_table "Data table") stored in a [router](https://en.wikipedia.org/wiki/Router_(computing) "Router (computing)") or a [network host](https://en.wikipedia.org/wiki/Network_host "Network host") that lists the routes to particular network destinations
- in some cases, [metrics](https://en.wikipedia.org/wiki/Metrics_(networking) "Metrics (networking)") (distances) associated with those routes
- f the node cannot directly connect to the destination node, it has to send it via other nodes along a route to the destination node
- node needs to keep track of which way to deliver various packages of data, and for this it uses a routing table
- Nodes can also share the contents of their routing table with other nodes