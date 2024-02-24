# [[transmission control protocol (TCP)]]
- protocol of the [[network layers#transport layer|transport layer]] 
- [[li connection based socket]]

![[stream communication#stream communication]]

## segement structure
- transmitted package maximal 1500 Bytes
- consists of header ([[transmission control protocol (TCP)|TCP]] information) and payload 

![[TCPSegmentHeader-1.png]]

### header
- length between 20 and 60 Byte

#### source [[port]] adress (2 Byte)
A 16-bit field that holds the port address of the application that is sending the data segment.   

#### destination [[port]] adress (2 Byte)
A 16-bit field that holds the port address of the application in the host that is receiving the data segment.  

#### sequence number (4 Byte) 
- consecutively number of the segments
- initilized randomly by the sender
- [[server]] and [[client]] have their own independent sequence numbers

#### acknowledgement number (4 Byte) 
- expected sequence number of the next segment
- present in every but the first segment seny by the [[client]]
- confirms togather with the **ACK flag** that the last segment was recieved
- is ignored in the **ACK flag** is not set

#### checksum (2 Byte)
- sum varity that the segment is correct transmittet 
This field holds the checksum for error control.
#### urgent pointer (2 Byte)
This field (valid only if the URG control flag is set) is used to point to data that is urgently required that needs to reach the receiving process at the earliest. The value of this field is added to the sequence number to get the byte number of the last urgent byte.

#### recieve window (2 Byte)
- also called maximum segment size MSS=1460 B

#### data offset (1 Byte)
- length of the header in 4 byte blocks
	→ indicates where the payload starts
This is a 4-bit field that indicates the length of the TCP header by a number of 4-byte words in the header, i.e if the header is 20 bytes(min length of TCP header), then this field will hold 5 (because 5 x 4 = 20) and the maximum length: 60 bytes, then it’ll hold the value 15(because 15 x 4 = 60). Hence, the value of this field is always between 5 and 15.   

#### control-frags (8 Bit)
control bits that control connection establishment, connection termination, connection abortion, flow control, mode of transfer etc
1) SYN (synchronize sequence number) flag
	- request to start a connection and synchronize with the provided sequence number
2) ACK (acknowledgement) flag
	- confirms togather with the **acknowledgement number** that the last segment was recieved
	- if it's not set the **acknowledgement number** is ignored
3) FIN (finish)
	- last segment from sender
4) RST (reset) flag
	- reset the connection
	- technical problems or rejection of connection e.g. when port not open
5) URG (urgent) flag
6) PSH (push) flag
	- Asks to push the buffered data to the receiving application.
7) CWR und ECE: for congestion controll

#### window size
This field tells the window size of the sending TCP in bytes

#### options and padding (0 to 40 Byte)
- usualy not used

### payload
- transmittet data and protocol information of [[network layers#application layer|application layer]] protocols like [[hypertext transfer protocol (HTTP)]])

### connection stablishment
![[Tcp_verbindung.png]]

### 3 way handshake

![[330px-Tcp-handshake.svg.png]]

### connection termination
![[TCP-Teardown.svg.png]]


## congestion controll
- which is used for controlling the flow of data when congestion has actually occurred.

## flow controll
- managing the rate of data transmission between two nodes to prevent a fast sender from overwhelming a slow receiver
- TCP uses a [sliding window](https://en.wikipedia.org/wiki/Sliding_window "Sliding window") flow control protocol.
- In each TCP segment, the receiver specifies in the _receive window_ field the amount of additionally received data (in bytes) that it is willing to buffer for the connection
- The sending host can send only up to that amount of data before it must wait for an acknowledgement and receive window update from the receiving host.



# anki

START
Basic
[[transmission control protocol (TCP)]] segement structure
- parts 
- structure of parts (11 + 1)
- control frags (8)
Back: 
## segement structure
- transmitted package maximal 1500 Bytes
- consists of header ([[transmission control protocol (TCP)|TCP]] information) and payload 

![[TCPSegmentHeader-1.png]]

### header
- length between 20 and 60 Byte

#### source [[port]] adress (2 Byte)
A 16-bit field that holds the port address of the application that is sending the data segment.   

#### destination [[port]] adress (2 Byte)
A 16-bit field that holds the port address of the application in the host that is receiving the data segment.  

#### sequence number (4 Byte) 
- consecutively number of the segments
- initilized randomly by the sender
- [[server]] and [[client]] have their own independent sequence numbers

#### acknowledgement number (4 Byte) 
- expected sequence number of the next segment
- present in every but the first segment seny by the [[client]]
- confirms togather with the **ACK flag** that the last segment was recieved
- is ignored in the **ACK flag** is not set

#### checksum (2 Byte)
- checksum for error control

#### urgent pointer (2 Byte)
This field (valid only if the URG control flag is set) is used to point to data that is urgently required that needs to reach the receiving process at the earliest. The value of this field is added to the sequence number to get the byte number of the last urgent byte.

#### recieve window (2 Byte)
- also called maximum segment size MSS

#### data offset (1 Byte)
- length of the header in 4 byte blocks
	→ indicates where the payload starts
This is a 4-bit field that indicates the length of the TCP header by a number of 4-byte words in the header, i.e if the header is 20 bytes(min length of TCP header), then this field will hold 5 (because 5 x 4 = 20) and the maximum length: 60 bytes, then it’ll hold the value 15(because 15 x 4 = 60). Hence, the value of this field is always between 5 and 15.   

#### control-frags (8 Bit)
control bits that control connection establishment, connection termination, connection abortion, flow control, mode of transfer etc
1) SYN (synchronize sequence number) flag
	- request to start a connection and synchronize with the provided sequence number
2) ACK (acknowledgement) flag
	- confirms togather with the **acknowledgement number** that the last segment was recieved
	- if it's not set the **acknowledgement number** is ignored
3) FIN (finish)
	- last segment from sender
4) RST (reset) flag
	- reset the connection
	- technical problems or rejection of connection e.g. when port not open
5) URG (urgent) flag
6) PSH (push) flag
	- Asks to push the buffered data to the receiving application.
7) CWR und ECE: for congestion controll

#### window size
This field tells the window size of the sending TCP in bytes

#### options and padding (0 to 40 Byte)
- usualy not used

### payload
- transmittet data and protocol information of [[network layers#application layer|application layer]] protocols like [[hypertext transfer protocol (HTTP)]]

![[TCPSegmentHeader-1 1.png]]

Tags: code network
<!--ID: 1708791364988-->
END