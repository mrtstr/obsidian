# IP v6
- version of the [[internet protocol (IP)]] with 16 byte long adress
- successor of [[ip V4]]
- fixed size headers with fewer fields than ip v4 but the possibility to add extenson headers
- packages can't be fragmented by notwork routers

## Fragmentation and maximum package size

- routers don't fragment packages like [[ip V4]] packages 
- if the package is too big the router (lager than the MTU) will reject the package and announce its maximum package size to the sender

## ip v6 package
- consists of header, extra heads and the payload

![[08122014.gif]]
### payload
less than 1500 byte-long due to a technology called Maximum Transmission Unit (MTU), which defines the maximum size of a packet that can pass through the link. However, IPv6 can carry larger payloads than 65,355

### extension headrs
- some featues that are included in [[ip V4]] directly are implemented with extra headers in [[ip V6]]
- since most packages don't have extension heads this is more efficient

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

### main header
- header length is fixed size 40 bytes

#### version (6 bit)
- 4 for ip v4 or 6 for ip v6

#### traffic class/priority (8 bit)
- number that determains the priority for processing the package
- value betreen 0 and 7: tranissin can be lowed down when there is a lot of traffic
- values between 8 and 15: realtime application → transmission cant be slowed down

#### Flow Label (20 bit)
- indicates to intermediate devices that a packet belongs to a specific sequence of packets between a source and a destination
- When the Flow label value is set to 0 means that the packet is not associated with any specific flow (normal: 0)
- can be used for real time applications
- still testen

#### Payload Length (16 bit)
- number of bytes that are following the main header (including extension headers)

#### Next Header (8 bit)
- indecates following extension heads

#### Hop Limit (8 bit)
- ensures a packet won't circulate the network indefinitely in case of a routing loop
- Each time a packet passes through a layer 3 device value is decremented by one
- When the value becomes 0, the packet is discarded. 
- default 255

#### Source-Address (128 bit)

#### Destination-Address (128 bit)

# anki

START
Basic
[[ip V6]]
- summary
- maximum package size and fragmentation
- package structure
- how is it extended
- header fields (8)
Back: 

- version of the [[internet protocol (IP)]] with 16 byte long adress
- successor of [[ip V4]]
- fixed size headers with fewer fields than ip v4 but the possibility to add extenson headers
- packages can't be fragmented by notwork routers

## Fragmentation and maximum package size

- routers don't fragment packages like [[ip V4]] packages 
- if the package is too big the router (lager than the MTU) will reject the package and announce its maximum package size to the sender

## ip v6 package
- consists of header, extra heads and the payload

![[extensonheaders.png]]
### payload
less than 1500 byte-long due to a technology called Maximum Transmission Unit (MTU), which defines the maximum size of a packet that can pass through the link. However, IPv6 can carry larger payloads than 65,355

### extension headrs
- some featues that are included in [[ip V4]] directly are implemented with extra headers in [[ip V6]]
- since most packages don't have extension heads this is more efficient

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

### main header
- header length is fixed size 40 bytes

#### version (6 bit)
- 4 for ip v4 or 6 for ip v6

#### traffic class/priority (8 bit)
- number that determains the priority for processing the package
- value betreen 0 and 7: tranissin can be lowed down when there is a lot of traffic
- values between 8 and 15: realtime application → transmission cant be slowed down

#### Flow Label (20 bit)
- indicates to intermediate devices that a packet belongs to a specific sequence of packets between a source and a destination
- When the Flow label value is set to 0 means that the packet is not associated with any specific flow (normal: 0)
- can be used for real time applications
- still testen

#### Payload Length (16 bit)
- number of bytes that are following the main header (including extension headers)

#### Next Header (8 bit)
- indecates following extension heads

#### Hop Limit (8 bit)
- ensures a packet won't circulate the network indefinitely in case of a routing loop
- Each time a packet passes through a layer 3 device value is decremented by one
- When the value becomes 0, the packet is discarded. 
- default 255.

#### Source-Address (128 bit)

#### Destination-Address (128 bit)
Tags: code linux
<!--ID: 1711304374280-->
END