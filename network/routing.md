https://en.wikipedia.org/wiki/Routing

- hop-by-hop routing, each routing table lists, for all reachable destinations
- he simple algorithm of relaying [packets](https://en.wikipedia.org/wiki/Packet_(information_technology) "Packet (information technology)") to their destination's next hop thus suffices to deliver data anywhere in a network. Hop-by-hop is the fundamental characteristic of the IP [Internet layer](https://en.wikipedia.org/wiki/Internet_layer "Internet layer")[[1]](https://en.wikipedia.org/wiki/Routing_table#cite_note-1) and the OSI [Network Layer](https://en.wikipedia.org/wiki/Network_Layer "Network Layer").

## directly connected networks
- A directly connected network is a network that is directly attached to one of the router interfaces → The network address and subnet mask of the interface, along with the interface type and number, are entered into the routing table as a directly connected network

## remote networks
- network that can only be reached by sending the packet to another router.
- Routing table entries to remote networks may be either dynamic or static
- Dynamic routes are routes to remote networks that were learned automatically by the router through a dynamic routing protocol. Static routes are routes that a network administrator manually configured

- need to record routes to large numbers of devices using limited storage space represents a major challenge in routing table construction
- currently dominant address aggregation technology is a bitwise prefix matching scheme called Classless Inter-Domain Routing (CIDR). Supernetworks can also be used to help control routing table size.

## switch
A networking device that connects devices on a network and forwards data packets between them.

## rounter
- A networking device that connects multiple networks together and forwards data packets between them
- primary function of a router is to forward a packet toward its destination network
- if the destination of a package is within another [[subnetwork]] the router will send it to the [[router]] of the desination [[subnetwork]]

## gateway
Translate from one protocol to other

## networkmask
- used for calculcation the network adress of a given [[internet protocol (IP)]] adress by connectiong the adress and the subnet mask with a bitwise and connection

$$
Networkadress = Adress \: \& \: Networkmask
$$
## networkadress


## routing table
- is a [data table](https://en.wikipedia.org/wiki/Data_table "Data table") stored in a [router](https://en.wikipedia.org/wiki/Router_(computing) "Router (computing)") or a [network host](https://en.wikipedia.org/wiki/Network_host "Network host") that lists the routes to particular network destinations
- in some cases, [metrics](https://en.wikipedia.org/wiki/Metrics_(networking) "Metrics (networking)") (distances) associated with those routes
- f the node cannot directly connect to the destination node, it has to send it via other nodes along a route to the destination node
- node needs to keep track of which way to deliver various packages of data, and for this it uses a routing table
- Nodes can also share the contents of their routing table with other nodes