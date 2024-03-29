
## [[port]]
- number that uniquely identifys a local connection endpoint unter a given network adress
- while the [[internet protocol (IP)|IP adress]] is a (remote) identifier in a network the port is a virtual local identifier to reach different services under this adress
- ports are locally managed by the operating system of the nodes while the IP is relevant for the routing from node to node
- port is opened or closed
- each of the known ports is assiciated with a [[transmission control protocol (TCP)]] or [[user datagram protocol (UDP)]]
### port ranges
- for [[transmission control protocol (TCP)|TCP]] and [[user datagram protocol (UDP)|UPD]] those ports are 16-bit unsigned number ranging from 0 to 65535

#### system/well-known ports
- reserved for the most commonly used services

| Port No | Port       | Protocol |
|:------- |:---------- |:-------- |
| 21      | FTP        | TCP      |
| 22      | SSH        | TCP      |
| 53      | DNS        | TCP, UDP |
| 67,68   | DHCP       | UDP      |
| 80      | HTTP       | TCP      |
| 443     | HTTPS      | TCP      |

#### registered/user posrts 1024 to 49151
- staticly association with a process or service does not change

| Port No | Port       | Protocol |
|:------- |:---------- |:-------- |
| 1194      | OpenVPN        | TCP      |
| 1723      | PPTP        | TCP      |

#### dynamic/private ports 49152 to 65535
- dynamicly assigned to a [[li process]] or service when needed (usually when the process or service is started)


# anki
START
Basic
- What is the difference between an [[internet protocol (IP)]] adress and a port?
- How are the concepts connected?
- What is identifiered by them?
Back: 
- while the [[internet protocol (IP)|IP adress]] is a (remote) identifier in a network the port is a virtual local identifier to reach different services under this adress
- ports are locally managed by the operating system of the nodes while the IP is relevant for the routing from node to node

Tags: mathematics
<!--ID: 1710614272481-->
END


START
Basic
port
- definition
- port ranges
- posts used for HTTP, HTTPS, SSH, FTP
Back: 
## [[port]]
- number that uniquely identifys a local connection endpoint unter a given network adress
- while the [[internet protocol (IP)|IP adress]] is a (remote) identifier in a network the port is a virtual local identifier to reach different services under this adress
- ports are locally managed by the operating system of the nodes while the IP is relevant for the routing from node to node
- port is opened or closed
- each of the known ports is assiciated with a [[transmission control protocol (TCP)]] or [[user datagram protocol (UDP)]]
### port ranges
- for [[transmission control protocol (TCP)|TCP]] and [[user datagram protocol (UDP)|UPD]] those ports are 16-bit unsigned number ranging from 0 to 65535

#### system/well-known ports
- reserved for the most commonly used services

| Port No | Port       | Protocol |
|:------- |:---------- |:-------- |
| 21      | FTP        | TCP      |
| 22      | SSH        | TCP      |
| 53      | DNS        | TCP, UDP |
| 67,68   | DHCP       | UDP      |
| 80      | HTTP       | TCP      |
| 443     | HTTPS      | TCP      |

#### registered/user posrts 1024 to 49151
- staticly association with a process or service does not change

| Port No | Port       | Protocol |
|:------- |:---------- |:-------- |
| 1194      | OpenVPN        | TCP      |
| 1723      | PPTP        | TCP      |

#### dynamic/private ports 49152 to 65535
- dynamicly assigned to a [[li process]] or service when needed (usually when the process or service is started)

Tags: mathematics
<!--ID: 1710669597274-->
END

# anki
START
Basic
[[li shell command]] for
- display all open ports
- display all sockets connected over a certain port x
Back: 

```bash
ss -l -t | grep LISTEN # TCP
ss -l -u | grep LISTEN # UDP
ss -l -u -t | grep LISTEN # both
```

```bash
lsof -i:443
```

## `ss`
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

## `lsof`
[[shell command]] `lsof` list all open [[li file descriptor|file descriptors]] 
```bash
lsof  # list all open file descriptors
	[-p PID]     # only open files of a specific process
	[-P]         # show used ports
	[-i [:port]]     # show only network file descriptors (and optionally filter for port)
	[-n]     # show ip adress instead of host name
```

```bash
lsof <path of file>  
# list all processes that have currently opened the given file
```

### provided information
#### `FD`: more information about the file descriptor
- `cwd` - current working directory
- `txt` - binary file
- `mem` - memory mapped file
- integer number for [[li standard streams]] and open [[li file|files]]
- opening mode: (`r` for read access, `w` for write access, `u` for read and write access)



Tags: mathematics
<!--ID: 1710696285368-->
END