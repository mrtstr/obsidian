# [[transmission control protocol (TCP)]]
- [[statefulness of protocols|stateful]] [[protocol]] of the [[osi layers#transport layer|transport layer]] for [[stream communication|stream based]] data transfer
- managed by the operation system with a [[li connection based socket]]

![[stream communication#stream communication]]

### TCP connection
- [[transmission control protocol (TCP)|TCP]] connection is defined by two service endpoints ([[internet protocol (IP)|IP adress]], [[port]]) 
	→ a TCP connection is identified by a 4-tuple (server ip, server port, client ip, client port)
- a [[li socket|TCP socket]] is a connection endpoint instance with an [[internet protocol (IP)|IP adress]] and a [[port]] (but not uniquely identified by them)
- a network service (address/port) can have multiple sockets but only one of them is [[li listen|listening]] to incomming connections requests
- appart from the [[li listen|listening]] [[li socket]] there can be multiple [[li socket|sockts]] that are connected

## segement structure
- transmitted package maximal 1500 Bytes
- consists of header ([[transmission control protocol (TCP)|TCP]] information) and payload 

![[TCPSegmentHeader-1.png]]

### header
- length between 20 and 60 Byte

#### source [[port]] adress (2 Byte)
- [[port]] address of the application that is sending the data segment

#### destination [[port]] adress (2 Byte)
- [[port]] address of the application in the host that is receiving the data segment

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
- checksum for error control.

#### urgent pointer (2 Byte)
- valid only if the URG control flag is set 
- pointer to the data that is urgently required (e.g. error messages)

#### recieve window (2 Byte)
- also called maximum segment size MSS=1460 B
- amount of data that a reciver can accept without acknowledging the sender

#### data offset (1 Byte)
- length of the header in 4 byte words
	→ indicates where the payload starts
- if the header is 20 Byte thsi field will hold 5

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
	- notify the reciver that a part of the data needs emidiate attention e.g. for error messages
	- part of the data that is urgent is indicated by the urgent pointer
6) PSH (push) flag
	- Asks to push the buffered data to the receiving application even if the buffer is not full
	- used for real time applications like voice over ip
	- reduces the latency
7) CWR und ECE: for congestion control

#### recive window size
- buffer size of the reciver
- Sie bemisst den freien Speicher im Empfangs[puffer](https://de.wikipedia.org/wiki/Puffer_(Informatik) "Puffer (Informatik)") eines Computers, und damit die maximale Datenmenge, die empfangen werden kann, bevor es zu einem [Pufferüberlauf](https://de.wikipedia.org/wiki/Puffer%C3%BCberlauf "Pufferüberlauf") kommt und weitere eingehende Pakete verworfen werden müssen

#### options and padding (0 to 40 Byte)
- can contain options like the maximum segment sizze (MMS)
- padding maked sure the header size is a multiple of 4 Byte

### payload
- transmittet data and protocol information of [[osi layers#application layer|application layer]] protocols like [[hypertext transfer protocol (HTTP)]]

### maximum segment sizze (MMS)
- parameter in the options field of the header
- secifies the largest amount of data that can recived as payload in a single TCP sement
- tradeoff between overhead and fragmentation in the [[internet protocol (IP)]] layer

## phases
- connection establishment
- data transfer
- termination

![[Tcp_verbindung.png]]

### connection stablishment
- 3 way handshake
1) the [[client]] sends a SYN with a radom initilized sequence number x
2) the [[server]] responds with a SYN-ACK by sendeing a sement with a ACK number x+1 and his own randomly initilizes sequence number y
3) the [[client]] confirms the sequence number of the server by acknolaging in with an ACK number of y+1



![[330px-Tcp-handshake.svg.png]]

### data transfer 
- phase when the data is transmitted

#### reliable transmission 
reliable and error free transmission is ganteed by
- sequenc number of each segment
- acknowledgement of recived segments 
- check sum

#### flow controll
- managing the rate of data transmission between two nodes to prevent a fast sender from overwhelming a slow receiver
- with each segment the sender gives its reciver window = free space in the buffer = abount of data that can still be sent without ACK of the reciver
- after the buffer is full the reciver will process the buffer and when the buffer is empty send a ACK to tell the sender that he is ready to recive again

#### congestion control
- lost packages will trigger a reduction in data delivery rate

### connection termination
- connection termination happens in a four way handshake
1) initiator send a FIN segment to initiate the termination of the connection
2) the reciver ACK the final segment of the reciver
3) the reciver sends a FIN segment with his last sement number
4) the initiator ACK the final segment of the reciver

![[TCP-Teardown.svg.png]]






# anki

START
Basic
[[transmission control protocol (TCP)]] 
- summary [[transmission control protocol (TCP)]]
- what is a TCP connection and how is it releated to a [[li socket]]?
- connection stablishment (3)
- data transfer (3 + 3 + 1)
- connection termination (4)
Back: 
### [[transmission control protocol (TCP)]] 
- [[statefulness of protocols|stateful]] [[protocol]] of the [[osi layers#transport layer|transport layer]] for [[stream communication|stream based]] data transfer
- managed by the operation system with a [[li connection based socket]]

#### [[stream communication]]
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

### TCP connection
- [[transmission control protocol (TCP)|TCP]] connection is defined by two service endpoints ([[internet protocol (IP)|IP adress]], [[port]]) 
	→ a TCP connection is identified by a 4-tuple (server ip, server port, client ip, client port)
- a [[li socket|TCP socket]] is a connection endpoint instance with an [[internet protocol (IP)|IP adress]] and a [[port]] (but not uniquely identified by them)
- a network service (address/port) can have multiple sockets but only one of them is [[li listen|listening]] to incomming connections requests
- appart from the [[li listen|listening]] [[li socket]] there can be multiple [[li socket|sockts]] that are connected

## phases

![[Tcp_verbindung 1.png]]

### connection stablishment
- 3 way handshake
1) the [[client]] sends a SYN with a radom initilized sequence number x
2) the [[server]] responds with a SYN-ACK by sendeing a sement with a ACK number x+1 and his own randomly initilizes sequence number y
3) the [[client]] confirms the sequence number of the server by acknolaging in with an ACK number of y+1

![[330px-Tcp-handshake.svg 1.png]]


### data transfer 
- phase when the data segments is transmitted

#### reliable transmission 
reliable and error free transmission is ganteed by
- sequenc number of each segment
- acknowledgement of recived segments 
- check sum

#### flow controll
- managing the rate of data transmission between two nodes to prevent a fast sender from overwhelming a slow receiver
- with each segment the sender gives its reciver window = free space in the buffer = abount of data that can still be sent without ACK of the reciver
- after the buffer is full the reciver will process the buffer and when the buffer is empty send a ACK to tell the sender that he is ready to recive again

#### congestion control
- lost packages will trigger a reduction in data delivery rate

### connection termination
- connection termination happens in a four way handshake
1) initiator send a FIN segment to initiate the termination of the connection
2) the reciver ACK the final segment of the reciver
3) the reciver sends a FIN segment with his last sement number
4) the initiator ACK the final segment of the reciver

![[TCP-Teardown.svg 1.png]]


Tags: code network
<!--ID: 1708873326983-->
END



START
Basic
[[transmission control protocol (TCP)]] summary
[[transmission control protocol (TCP)]] segement structure
- parts 
- structure of parts (11 + 1)
- control frags (8)
Back: 
### [[transmission control protocol (TCP)]] 
- [[statefulness of protocols|stateful]] [[protocol]] of the [[osi layers#transport layer|transport layer]] for [[stream communication|stream based]] data transfer
- managed by the operation system with a [[li connection based socket]]

#### [[stream communication]]
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

## segement structure
- transmitted package maximal 1500 Bytes
- consists of header ([[transmission control protocol (TCP)|TCP]] information) and payload 

![[TCPSegmentHeader-1 1.png]]

### header
- length between 20 and 60 Byte

#### source [[port]] adress (2 Byte)
- [[port]] address of the application that is sending the data segment

#### destination [[port]] adress (2 Byte)
- [[port]] address of the application in the host that is receiving the data segment

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
- checksum for error control.

#### urgent pointer (2 Byte)
- valid only if the URG control flag is set 
- pointer to the data that is urgently required (e.g. error messages)

#### recieve window (2 Byte)
- also called maximum segment size MSS=1460 B
- amount of data that a reciver can accept without acknowledging the sender

#### data offset (1 Byte)
- length of the header in 4 byte words
	→ indicates where the payload starts
- if the header is 20 Byte thsi field will hold 5

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
	- notify the reciver that a part of the data needs emidiate attention e.g. for error messages
	- part of the data that is urgent is indicated by the urgent pointer
6) PSH (push) flag
	- Asks to push the buffered data to the receiving application even if the buffer is not full
	- used for real time applications like voice over ip
	- reduces the latency
7) CWR und ECE: for congestion controll

#### recive window size
- buffer size of the reciver
- Sie bemisst den freien Speicher im Empfangs[puffer](https://de.wikipedia.org/wiki/Puffer_(Informatik) "Puffer (Informatik)") eines Computers, und damit die maximale Datenmenge, die empfangen werden kann, bevor es zu einem [Pufferüberlauf](https://de.wikipedia.org/wiki/Puffer%C3%BCberlauf "Pufferüberlauf") kommt und weitere eingehende Pakete verworfen werden müssen

#### options and padding (0 to 40 Byte)
- can contain options like the maximum segment sizze (MMS)
- padding maked sure the header size is a multiple of 4 Byte

### payload
- transmittet data and protocol information of [[osi layers#application layer|application layer]] protocols like [[hypertext transfer protocol (HTTP)]]

### payload
- transmittet data and protocol information of [[osi layers#application layer|application layer]] protocols like [[hypertext transfer protocol (HTTP)]]

Tags: code network
<!--ID: 1708791364988-->
END



START
Basic
[[transmission control protocol (TCP)]]: maximum window size
- what is it
- how is it set
- what influences the desiccion

Back: 

### maximum segment sizze (MMS)
- parameter in the options field of the header
- secifies the largest amount of data that can recived as payload in a single TCP sement
- tradeoff between overhead and fragmentation in the [[internet protocol (IP)]] layer


Tags: code network
<!--ID: 1708873326988-->
END


START
Basic
[[transmission control protocol (TCP)]]
- how does it make sure the transmission is reliable and error free?
- how does it make sure the network is not overloaded?
- how does it make sure the reciver is not overwhelmed?

Back: 
#### reliable transmission 
reliable and error free transmission is ganteed by
- sequenc number of each segment
- acknowledgement of recived segments 
- check sum

#### flow controll
- managing the rate of data transmission between two nodes to prevent a fast sender from overwhelming a slow receiver
- with each segment the sender gives its reciver window = free space in the buffer = abount of data that can still be sent without ACK of the reciver
- after the buffer is full the reciver will process the buffer and when the buffer is empty send a ACK to tell the sender that he is ready to recive again

#### congestion control
- lost packages will trigger a reduction in data delivery rate

Tags: code network
<!--ID: 1708873326991-->
END


START
Basic
[[transmission control protocol (TCP)]]
- 8 flags in the control block of the header

Back: 
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
	- notify the reciver that a part of the data needs emidiate attention e.g. for error messages
	- part of the data that is urgent is indicated by the urgent pointer
6) PSH (push) flag
	- Asks to push the buffered data to the receiving application even if the buffer is not full
	- used for real time applications like voice over ip
	- reduces the latency
7) CWR und ECE: for congestion control

Tags: code network
<!--ID: 1708873326995-->
END


START
Basic
[[transmission control protocol (TCP)]]
- how does it make sure data is processed fast in real time application?
- how does it make sure things like error messages or control frags are processed immediately?

Back: 
- for real time applcations the push (PSH) flag is set to make sure the data is processed  emediatly even when the buffer is not full
- for urgent data the urgent pointer is set to the data and the urgent (URG) flag is set

### header
- length between 20 and 60 Byte

#### source [[port]] adress (2 Byte)
- [[port]] address of the application that is sending the data segment

#### destination [[port]] adress (2 Byte)
- [[port]] address of the application in the host that is receiving the data segment

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
- checksum for error control.

#### urgent pointer (2 Byte)
- valid only if the URG control flag is set 
- pointer to the data that is urgently required (e.g. error messages)

#### recieve window (2 Byte)
- also called maximum segment size MSS=1460 B
- amount of data that a reciver can accept without acknowledging the sender

#### data offset (1 Byte)
- length of the header in 4 byte words
	→ indicates where the payload starts
- if the header is 20 Byte thsi field will hold 5

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
	- notify the reciver that a part of the data needs emidiate attention e.g. for error messages
	- part of the data that is urgent is indicated by the urgent pointer
6) PSH (push) flag
	- Asks to push the buffered data to the receiving application even if the buffer is not full
	- used for real time applications like voice over ip
	- reduces the latency
7) CWR und ECE: for congestion control

#### recive window size
- buffer size of the reciver
- Sie bemisst den freien Speicher im Empfangs[puffer](https://de.wikipedia.org/wiki/Puffer_(Informatik) "Puffer (Informatik)") eines Computers, und damit die maximale Datenmenge, die empfangen werden kann, bevor es zu einem [Pufferüberlauf](https://de.wikipedia.org/wiki/Puffer%C3%BCberlauf "Pufferüberlauf") kommt und weitere eingehende Pakete verworfen werden müssen

#### options and padding (0 to 40 Byte)
- can contain options like the maximum segment sizze (MMS)
- padding maked sure the header size is a multiple of 4 Byte

Tags: code network
<!--ID: 1708873326998-->
END