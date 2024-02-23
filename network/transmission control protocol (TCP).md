## [[transmission control protocol (TCP)]]
- protocol of the [[network layers#transport layer|transport layer]] 
- [[li connection based socket]]

![[stream communication#stream communication]]

### connection stablishment
-   **Step 1 (SYN):** In the first step, the client wants to establish a connection with a server, so it sends a segment with SYN(Synchronize Sequence Number) which informs the server that the client is likely to start communication and with what sequence number it starts segments with
-   **Step 2 (SYN + ACK):** A port is the logical address of any protocol; alternatively, we might think of a port as a special door for each protocol, through which all packets are routed. Another way to put it is that every protocol has a mailbox, or box, where every protocol packet is dropped. Subsequently, the recipient will access that packet and peruse the content sent by the sender. Every protocol has a port, which is a specific line used for packet transfer.

In this article, we are going to discuss TCP/IP Port as well as the types of TCP/IP Port.
-   **Step 3 (ACK):** In the final part client acknowledges the response of the server and they both establish a reliable connection with which they will start the actual data transfer
![[net.png]]

### connection termination

### segment structure
-   **Source Port Address –**   
A 16-bit field that holds the port address of the application that is sending the data segment.   
 
-   **Destination Port Address –**   
A 16-bit field that holds the port address of the application in the host that is receiving the data segment.   
 
-   **Sequence Number –**   
A 32-bit field that holds the sequence number, i.e, the byte number of the first byte that is sent in that particular segment. It is used to reassemble the message at the receiving end of the segments that are received out of order.   
 
-   **Acknowledgement Number –**   
A 32-bit field that holds the acknowledgement number, i.e, the byte number that the receiver expects to receive next. It is an acknowledgement for the previous bytes being received successfully.   
 
-   **Header Length (HLEN) –**   
This is a 4-bit field that indicates the length of the TCP header by a number of 4-byte words in the header, i.e if the header is 20 bytes(min length of TCP header), then this field will hold 5 (because 5 x 4 = 20) and the maximum length: 60 bytes, then it’ll hold the value 15(because 15 x 4 = 60). Hence, the value of this field is always between 5 and 15.   
 
-   **Control flags –**   
These are 6 1-bit control bits that control connection establishment, connection termination, connection abortion, flow control, mode of transfer etc. Their function is:   
-   URG: Urgent pointer is valid
-   ACK: Acknowledgement number is valid( used in case of cumulative acknowledgement)
-   PSH: Request for push
-   RST: Reset the connection
-   SYN: Synchronize sequence numbers
-   FIN: Terminate the connection
-   **Window size –**   
This field tells the window size of the sending TCP in bytes.   
 
-   **Checksum –**   
This field holds the checksum for error control. It is mandatory in TCP as opposed to UDP.   
 
-   **Urgent pointer –**   
This field (valid only if the URG control flag is set) is used to point to data that is urgently required that needs to reach the receiving process at the earliest. The value of this field is added to the sequence number to get the byte number of the last urgent byte.

![[TCPSegmentHeader-1.png]]




### flow controll