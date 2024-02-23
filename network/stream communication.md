### [[stream communication]]
- **Byte-Oriented**: 
	- data treatet as a continuous stream of bytes
		→ no message boundaries, 
		→ the receiver must handle message framing
- **Ordered and Reliable**
	- Data delivery is guaranteed and in order
		→ If a packet is lost or corrupted, it will be retransmitted
- **Connection-Oriented**: 
	- connection between the sender and receiver has to be stablished before data transfer
- **Flow Control**: 
	- prevent sender from overwhelming the receiver
- e.g. [[transmission control protocol (TCP)]] used in [[li connection based socket]] (`SOCK_STREAM` and `SOCK_SEQPACKET`)


# anki

START
Basic
two of communication concepts with example protocols
Back: 
### [[stream communication]]
- **Byte-Oriented**: 
	- data treatet as a continuous stream of bytes
		→ no message boundaries, 
		→ the receiver must handle message framing
- **Ordered and Reliable**
	- Data delivery is guaranteed and in order
		→ If a packet is lost or corrupted, it will be retransmitted
- **Connection-Oriented**: 
	- connection between the sender and receiver has to be stablished before data transfer
- **Flow Control**: 
	- prevent sender from overwhelming the receiver
- e.g. [[transmission control protocol (TCP)]] used in [[li connection based socket]] (`SOCK_STREAM` and `SOCK_SEQPACKET`)

### [[datagram]]
- **Connectionless**
	- no initial connection setup
	- each packet is treated independently
- **Unreliable**
	- no guarantee for delivery and order of packets. 
- **Message-Oriented**
	- preserve message boundaries
		→ Each send() call corresponds to one receive() call on the other end.
- **No Flow Control**
	- no inherent flow control mechanism
	- application to implement flow control if needed.
- e.g. [[user datagram protocol (UDP)]] used in `SOCK_DGRAM` [[li conection less socket]]
Tags: code linux
<!--ID: 1708682546582-->
END