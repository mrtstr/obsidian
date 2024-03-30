## router
- A [[network|networking]] device that connects multiple [[network|networks]] together and forwards data packets between them
	→ selecting paths for data packets to cross [[network|networks]] 
	- (within the [[network]] [[switch|swiches]] are used to distribute the packages but most [[router|routers]] have swiches included and thus have multiple [[ethernet]] ports)
- works on the [[osi layers|network layer]] using the [[internet protocol (IP)]] adress
- routes are found by **hop-by-hop routing** where reach [[router]] forwards the package to the next closes [[network]] in its routing table
- **directly connected [[network]]**: [[network]] to which the [[router]] is directly connected
- **remote [[network]]**: can only be reached by sending the packet to another router.

### routing table
- table stored in a [[router]] containing routes to [[network]] destinations and some properties of them
- **dynamic routing table entry**: learned by the [[router]] by communicating with other [[router|routers]]
- **static routing table entry**: manuelly defined
- contrains
	- destination [[network adress]]
	- [[networkmask]]
	- gateway/next hop = destination can be optimally reached by sending the packet to a specific this [[network adress]]
	- routing distance metric: how long does it take to reach the destination

![[routing_table.png]]


# anki

START
Basic
- what does a [[router]] do?
- what is the difference to a [[switch]]?
- on which [[network layer]] does it operate?
- how does a [[router]] determins routes?
Back: 
## router
- A [[network|networking]] device that connects multiple [[network|networks]] together and forwards data packets between them
	→ selecting paths for data packets to cross [[network|networks]] 
	- (within the [[network]] [[switch|swiches]] are used to distribute the packages but most [[router|routers]] have swiches included and thus have multiple [[ethernet]] ports)
- works on the [[osi layers|network layer]] using the [[internet protocol (IP)]] adress
- routes are found by **hop-by-hop routing** where reach [[router]] forwards the package to the next closes [[network]] in its routing table
- **directly connected [[network]]**: [[network]] to which the [[router]] is directly connected
- **remote [[network]]**: can only be reached by sending the packet to another router.

### routing table
- table stored in a [[router]] containing routes to [[network]] destinations and some properties of them
- **dynamic routing table entry**: learned by the [[router]] by communicating with other [[router|routers]]
- **static routing table entry**: manuelly defined
- contrains
	- destination [[network adress]]
	- [[networkmask]]
	- gateway/next hop = destination can be optimally reached by sending the packet to a specific this [[network adress]]
	- routing distance metric: how long does it take to reach the destination

![[routing_table 1.png]]

Tags: code network
<!--ID: 1711813346662-->
END


START
Basic
- what is a routering table?
- how is it used?
- how is it filled?L
- what does it contain? (4)
Back: 
## router
- A [[network|networking]] device that connects multiple [[network|networks]] together and forwards data packets between them
	→ selecting paths for data packets to cross [[network|networks]] 
	- (within the [[network]] [[switch|swiches]] are used to distribute the packages but most [[router|routers]] have swiches included and thus have multiple [[ethernet]] ports)
- works on the [[osi layers|network layer]] using the [[internet protocol (IP)]] adress
- routes are found by **hop-by-hop routing** where reach [[router]] forwards the package to the next closes [[network]] in its routing table
- **directly connected [[network]]**: [[network]] to which the [[router]] is directly connected
- **remote [[network]]**: can only be reached by sending the packet to another router.

### routing table
- table stored in a [[router]] containing routes to [[network]] destinations and some properties of them
- **dynamic routing table entry**: learned by the [[router]] by communicating with other [[router|routers]]
- **static routing table entry**: manuelly defined
- contrains
	- destination [[network adress]]
	- [[networkmask]]
	- gateway/next hop = destination can be optimally reached by sending the packet to a specific this [[network adress]]
	- routing distance metric: how long does it take to reach the destination

![[routing_table 2.png]]

Tags: code network
<!--ID: 1711813346666-->
END