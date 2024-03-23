# ip v4
## Fragmentation
![[ipv4-fragmentation-example.gif]]
- In IPv4, all network layer devices are allowed to fragment packets (if the DF-bit (don't fragment) is not set)
- For example, if a router receives a packet that is larger than the MTU of the outgoing interface, the router divides the packet into multiple packets and send them out.
- The final destination is then responsible to reassemble the fragments into the original IP packet.
- The three IPv4 fields **_Identification_**, **_Flags_**, and **_Fragmentation Offset_** are used in this fragmentation handling process.
- he message includes the MTU value of the egress link, so the source can adjust the packet size and retransmit. This process is called Path MTU Discovery

## ip packet v4
consists of header and data

### ip header
- variable length size of the IPv4 header
![[comparing-ipv4-and-ipv6-headers.png]]

### ip data

