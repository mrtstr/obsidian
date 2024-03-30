- a [[gateway]] translates converts between [[osi layers#data link layer|data link layer]] network protocol
- a [[router]] is distributing packages across networks
	→ a [[gateway]] connects networks ([[router]]) with different protocol's
- a [[switch]] distributes data within a network

1) the package is sent from a host to the [[router]] of its [[network]]
2) (optional) there can be a [[switch]] between [[router]] and host 
3) the [[router]] sends the package to the [[router]] of the recipients hosts [[network]] (direct or via other networks)
4) there might be a [[gateway]] between the [[router|routers]] translating network protocols
5) the [[router]] of the reciving [[network]] will send the package to its destiantion

`host A` → `switch` → `router` → `gateway` → `router`→ `switch` → `host B`

![[switch#switch]]

![[gateway#gateway]]

![[router#router]]

# anki

START
Basic
[[gateway]], [[router]] and [[switch]]
- what are they doing?
- How are they working togather in [[network|networks]]?
- on which [[osi layers]] do they operate?
Back: 
- a [[gateway]] translates converts between [[osi layers#data link layer|data link layer]] network protocol
- a [[router]] is distributing packages across networks
	→ a [[gateway]] connects networks ([[router]]) with different protocol's
- a [[switch]] distributes data within a network


1) the package is sent from a host to the [[router]] of its [[network]]
2) (optional) there can be a [[switch]] between [[router]] and host 
3) the [[router]] sends the package to the [[router]] of the recipients hosts [[network]] (direct or via other networks)
4) there might be a [[gateway]] between the [[router|routers]] translating network protocols
5) the [[router]] of the reciving [[network]] will send the package to its destiantion

`host A` → `switch` → `router` → `gateway` → `router`→ `switch` → `host B`

### gateway
- network device that traslates from one [[network|network]] protocol to another
- on the [[osi layers#data link layer|data link layer]]
- needed when sending packages from one [[network]] to another that is using a different protocol
	→ not needed when sending data withing a network 
- is needed for connection [[router|routers]]

### switch
- device [[network|networking]] that multiplexes data packages to devices (destination node or other [[switch]]) within a [[network|network]]
- works on the [[osi layers#data link layer|data link layer]] based on [[media access code (MAC)]] or on the [[osi layers#network layer|network layer]] mased on the [[internet protocol (IP)]] adress
- [[router|routers]] usually have swiches included thus they have multiple [[ethernet]] ports thus no dedicated swich is needed in a home network

### [[router]]
- A [[network|networking]] device that connects multiple [[network|networks]] together and forwards data packets between them
	→ selecting paths for data packets to cross [[network|networks]] 
- if the destination of a package is within another [[subnetwork]] the router will send it to the [[router]] of the desination [[subnetwork]]
- within the network [[switch|swiches]] are used to distribute the packages (most [[router|routers]] have swiches included and thus have multiple [[ethernet]] ports)
- works on the [[osi layers|network layer]] using the [[internet protocol (IP)]] adress

#### network layer
- Structuring and managing a multi-node network
	→ [[adressing]], [[networking devices]], [[network traffic control]]
- e.g. [[internet protocol (IP)]]

#### data link layer
- phsical connection between nodes using e.g. data link [[switch|swiches]]
- makes sure the data get transmitted physicly to the right destination within a network
- works on [[media access code (MAC)]] level

Tags: code network
<!--ID: 1711734993928-->
END


