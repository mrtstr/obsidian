## router
### definition
- A [[network|networking]] device that connects multiple [[network|networks]] together and forwards data packets between them
	→ selecting paths for data packets to cross [[network|networks]] 
- if the destination of a package is within another [[subnetwork]] the router will send it to its [[network adress]] where the other [[router]] recives it
- within the [[network]] [[switch|swiches]] are used to distribute the packages (most [[router|routers]] have swiches included and thus have multiple [[ethernet]] ports)
- works on the [[osi layers|network layer]] using the [[internet protocol (IP)]] adress


#### directly connected networks
- A directly connected network is a network that is directly attached to one of the router interfaces → The network address and subnet mask of the interface, along with the interface type and number, are entered into the routing table as a directly connected network

#### remote networks
- network that can only be reached by sending the packet to another router.
- Routing table entries to remote networks may be either dynamic or static
- Dynamic routes are routes to remote networks that were learned automatically by the router through a dynamic routing protocol. Static routes are routes that a network administrator manually configured

- need to record routes to large numbers of devices using limited storage space represents a major challenge in routing table construction
- currently dominant address aggregation technology is a bitwise prefix matching scheme called Classless Inter-Domain Routing (CIDR). Supernetworks can also be used to help control routing table size.

### routing table
- is a [data table](https://en.wikipedia.org/wiki/Data_table "Data table") stored in a [router](https://en.wikipedia.org/wiki/Router_(computing) "Router (computing)") or a [network host](https://en.wikipedia.org/wiki/Network_host "Network host") that lists the routes to particular network destinations
- in some cases, [metrics](https://en.wikipedia.org/wiki/Metrics_(networking) "Metrics (networking)") (distances) associated with those routes
- f the node cannot directly connect to the destination node, it has to send it via other nodes along a route to the destination node
- node needs to keep track of which way to deliver various packages of data, and for this it uses a routing table
- Nodes can also share the contents of their routing table with other nodes
this refers to the outgoing interface that connects to the destination
![[routing_table.png]]