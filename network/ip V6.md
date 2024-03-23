# IP v6
- 16 byte long adress instead of 4
- fixed size headers with fewer fields than ip v4 but the possibility to add extenson headers
- packages can't be fragmented by notwork routers
- if the package is too big the router/MTU will reject the packet and announce its maximum package size to the sender

## Fragmentation and maximum package size
![[ipv6-fragmentation.gif]]

- In IPv6, routers do not fragment packets.
- When an IPv6 router receives a packet larger than the MTU of the outgoing interface, the router discards the packet and sends an ICMPv6 "Packet Too Big" message back to the sender.


## ip packet v6
n IPv6, there is no **Checksum field**. because transport layer already has that

### ip header
- header length is fixed size 40 bytes
- IPv6 is using two main types of headers: Main IPv6 Header and the new IPv6 Extension Headers. The main IPv6 header is equivalent to the IPv4 one with some field differences introduced for better efficiency. Figure 1 compares both headers.
- enthält, die für das IP-Routing wichtig sind.
- Optionale Informationen sind in einem oder mehreren Extension Headers ausgelagert, die sich zwischen Header und Payload befinden




#### version (6 bit)
- 4 for ip v4 or 6 for ip v6
#### Traffic Class/Priority (8 bit)
- legt für jedes Paket eine Priorität in der Flussteuerung fest
- Die Prioritätswerte lassen sich in zwei Gruppen aufteilen. Ein Wert von 0 bis 7 steht für Pakete, deren Übertragung sich bei hoher Netzwerkbelastung verlangsamen darf.
- Werte von 8 bis 15 hingegen signalisieren, dass ein Paket zu einer Echtzeitanwendung gehört und möglichst schnell weitergeleitet werden muss. Innerhalb einer Gruppe sind jeweils höhere Prioritätswerte wichtiger.
#### Flow Label (20 bit)
- The Flow Label is a 20-bit long field that indicates to intermediate devices that a packet belongs to a specific sequence of packets between a source and a destination
- IPv6 routers use this field to distinguish different traffic flow between the same source and destination, for example, different TCP sessions between the same endpoints.
- When the Flow label value is set to 0 means that the packet is not associated with any specific flow.
- normal packages 0
- can be used for real time applications
#### Payload Length (16 bit)
- gibt an, wie viele Bytes dem festen Header folgen

#### Next Header (8 bit)
- eigt an, welcher Erweiterungs-Header dem festen Header folgt

- The IPv6 Payload field is a 16-bit identifier of the length in bytes of the data portion of a packet including any IPv6 Extension headers. The length does not include the main IPv6 header.

![[08122014.gif]]


| Nummer | Extension Header                     |
| ------ | ------------------------------------ |
| 0      | Hop-by-Hop Options                   |
| 43     | Routing                              |
| 44     | Fragment                             |
| 51     | Authentication Header (AH)           |
| 50     | Encapsulation Security Payload (ESP) |
| 60     | Destination Options                  |
| 135    | Mobility                             |
| 139    | Host Identity Protocol               |
| 140    | Shim6 Protocol                       |



#### Hop Limit ()
- ensures a packet won't circulate the network indefinitely in case of a routing loop
- Each time a packet passes through a layer 3 device, the TTL value is decremented by one
- When the value becomes 0, the packet is discarded. By default, the TTL value is set to 255.
#### Source-Address 128 bit

#### Destination-Address 128
### ip data
less than 1500 byte-long due to a technology called Maximum Transmission Unit (MTU), which defines the maximum size of a packet that can pass through the link. However, IPv6 can carry larger payloads than 65,355