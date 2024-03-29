### `ss`
- [[li socket|socket]] statistics
- displaying detailed information about network sockets
#### displayed information
- **netid**: [[osi layers#transport layer|transport layer protocol]] and [[li socket#type|socket type]]
	- [[li unix domain socket]]: `u_str` for `SOCK_STREAM` and `u_dgr` for `SOCK_DRAM`
	- [[li internet domain socket]]: [[transmission control protocol (TCP)|tcp]] or [[user datagram protocol (UDP)|udp]] 
- **connection state**
- **Recv-Q**: It is the number of bytes that are currently in a receive buffer
- **Send-Q**: data which the sending application has given to the transport, but has yet to be ACKnowledged by the receiving TCP
- **Local Address:Port**
- **Peer Address:Port**
- **[[li process|process]]**

#### filter for [[osi layers#transport layer|transport layer protocol]]
```bash
ss
	[-t] # Display TCP sockets
	[-u] # Display UDP sockets
```

#### filter for [[osi layers#network layer|network protocol]]
```bash
ss
	[-4] # Display only IPv4 sockets
	[-6] # Display only IPv6 sockets
	[-x] # Display only unix sockets
```

#### filter for connection state
```bash
ss
	[-l] # Display listening sockets
	[-a] # Display listening and non-listening
	[-e] # Display exclusively established connections
```

#### show addtional information
```bash
ss  
	[-n] # Show numerical addresses instead of resolving
	[-r] # Show resolved addresses (default)
	[-p] # show information about he process
```

# anki
START
Basic
how to display connections?
filter for [[osi layers#transport layer|transport layer protocol]]
filter for [[osi layers#network layer|network protocol]]
filter for connection state
show addtional information
Back: 
### `ss`
- [[li socket|socket]] statistics
- displaying detailed information about network sockets
#### displayed information
- **netid**: [[osi layers#transport layer|transport layer protocol]] and [[li socket#type|socket type]]
	- [[li unix domain socket]]: `u_str` for `SOCK_STREAM` and `u_dgr` for `SOCK_DRAM`
	- [[li internet domain socket]]: [[transmission control protocol (TCP)|tcp]] or [[user datagram protocol (UDP)|udp]] 
- **connection state**
- **Recv-Q**: It is the number of bytes that are currently in a receive buffer
- **Send-Q**: data which the sending application has given to the transport, but has yet to be ACKnowledged by the receiving TCP
- **Local Address:Port**
- **Peer Address:Port**
- **[[li process|process]]**

#### filter for [[osi layers#transport layer|transport layer protocol]]
```bash
ss
	[-t] # Display TCP sockets
	[-u] # Display UDP sockets
```

#### filter for [[osi layers#network layer|network protocol]]
```bash
ss
	[-4] # Display only IPv4 sockets
	[-6] # Display only IPv6 sockets
	[-x] # Display only unix sockets
```

#### filter for connection state
```bash
ss
	[-l] # Display listening sockets
	[-a] # Display listening and non-listening
	[-e] # Display exclusively established connections
```

#### show addtional information
```bash
ss  
	[-n] # Show numerical addresses instead of resolving
	[-r] # Show resolved addresses (default)
	[-p] # show information about he process
```

Tags: code linux
<!--ID: 1710696285377-->
END

START
Basic
`ss`
- what does it do?
- displayed information (6)
- flags (11)
Back: 
### `ss`
- [[li socket|socket]] statistics
- displaying detailed information about network sockets
#### displayed information
- **netid**: [[osi layers#transport layer|transport layer protocol]] and [[li socket#type|socket type]]
	- [[li unix domain socket]]: `u_str` for `SOCK_STREAM` and `u_dgr` for `SOCK_DRAM`
	- [[li internet domain socket]]: [[transmission control protocol (TCP)|tcp]] or [[user datagram protocol (UDP)|udp]] 
- **connection state**
- **Recv-Q**: It is the number of bytes that are currently in a receive buffer
- **Send-Q**: data which the sending application has given to the transport, but has yet to be ACKnowledged by the receiving TCP
- **Local Address:Port**
- **Peer Address:Port**
- **[[li process|process]]**

#### filter for [[osi layers#transport layer|transport layer protocol]]
```bash
ss
	[-t] # Display TCP sockets
	[-u] # Display UDP sockets
```

#### filter for [[osi layers#network layer|network protocol]]
```bash
ss
	[-4] # Display only IPv4 sockets
	[-6] # Display only IPv6 sockets
	[-x] # Display only unix sockets
```

#### filter for connection state
```bash
ss
	[-l] # Display listening sockets
	[-a] # Display listening and non-listening
	[-e] # Display exclusively established connections
```

#### show addtional information
```bash
ss  
	[-n] # Show numerical addresses instead of resolving
	[-r] # Show resolved addresses (default)
	[-p] # show information about he process
```

Tags: code linux
<!--ID: 1710696285381-->
END