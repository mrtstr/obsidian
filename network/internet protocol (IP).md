# [[internet protocol (IP)]]
- protocol in the [[osi layers#network layer|network layer]]
- adressing inside networks → multiplexing from one node to another
- wrappes the transport layer segment ([[transmission control protocol (TCP)]], [[user datagram protocol (UDP)]])
- tro versions: ip v4 and ip v6

## ip adress
- consists of network adress/prefix (most significant bits) and host adress 
- host adressspace can be devided further into subnets
```
<network adress><host adress>
<network adress><subnet adress><host adress>
```

## routing
Eine _Route_ definiert einen Pfad für das Senden von Paketen über das Internet-Netz an eine Adresse in einem anderen Netz.

Eine Route definiert nicht den vollständigen Pfad, sondern nur das Pfadsegment von einem Host zu einem Gateway, das Pakete an ein Ziel weiterleiten kann (oder von einem Gateway zu einem anderen). Es gibt fünf Arten von Routen:

![[ip V6#IP v6]]

![[ip V4#ip v4]]


# anki

START
Basic
[[internet protocol (IP)]] fragmentation
- conecept
- difference in [[ip V6]] and [[ip V4]]
- releationship to the package size
Back: 
- splitting up packages by the [[networking devices|router]] that are larger than the maximum package size of the router (MTU) 

#### [[ip V4]]
- all network layer devices are allowed to fragment packets (if the DF-bit (don't fragment) is not set)
- For example, if a router receives a packet that is larger than the MTU of the outgoing interface, the router divides the packet into multiple packets and send them out.
- The final destination is then responsible to reassemble the fragments into the original IP packet
- The three IPv4 fields **_Identification_**, **_Flags_**, and **_Fragmentation Offset_** are used in this fragmentation handling process.
- he message includes the MTU value of the egress link, so the source can adjust the packet size and retransmit. This process is called Path MTU Discovery
#### [[ip V6]]
- routers don't fragment packages like [[ip V4]] packages 
- if the package is too big the router (lager than the MTU) will reject the package and announce its maximum package size to the sender

#### package size tradeoff
- large packages have less [[transmission control protocol (TCP)]] overhead but can lead to more ip fragmentation

Tags: code network
<!--ID: 1711304374285-->
END

START
Basic
[[internet protocol (IP)]] 
- difference in [[ip V6]] and [[ip V4]]

Back: 
- [[ip V6]] has a 16 byte long adress (more possible adresses) while [[ip V4]] has just 4 byte
- [[ip V6]] has a fixed size main headers with fewer fields than [[ip V4]] because extra features are implemented with extra headers
- [[ip V4]] has more field with more functions directly included

- [[ip V4]]: all network layer devices are allowed to fragment packets (if the DF-bit (don't fragment) is not set
- [[ip V6]]: routers don't fragment packages like [[ip V4]] packages 
	→ if the package is too big the router (lager than the MTU) will reject the package and announce its maximum package size to the sender

![[comparing-ipv4-and-ipv6-headers 1.png]]

Tags: code network
<!--ID: 1711304374289-->
END