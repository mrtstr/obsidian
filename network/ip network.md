## directly connected networks
- A directly connected network is a network that is directly attached to one of the router interfaces → The network address and subnet mask of the interface, along with the interface type and number, are entered into the routing table as a directly connected network

## remote networks
- network that can only be reached by sending the packet to another router.
- Routing table entries to remote networks may be either dynamic or static
- Dynamic routes are routes to remote networks that were learned automatically by the router through a dynamic routing protocol. Static routes are routes that a network administrator manually configured

- need to record routes to large numbers of devices using limited storage space represents a major challenge in routing table construction
- currently dominant address aggregation technology is a bitwise prefix matching scheme called Classless Inter-Domain Routing (CIDR). Supernetworks can also be used to help control routing table size.

## subnetting 
- Subnetting ist der Prozess, bei dem das größere Netzwerk in kleinere Subnetzwerke (Subnetze) aufgeteilt wird.
	- more efficinent since less broadcast traffic
	- simpler and thus easier to debug
- each subet has its network adress and its broadcast adress
