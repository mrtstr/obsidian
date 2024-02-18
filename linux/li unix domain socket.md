## [[li unix domain socket]]
 - AF_LOCAL/AF_UNIX [[li socket|sockets]] allow [[li process|processes]] to communicate with one another on a single system (independent of [[transmission control protocol (TCP)|TCP]]/[[IP|IP]])


- The **AF_UNIX** (also known as **AF_LOCAL**) socket family is used to communicate between processes on the same machine efficiently.
- Traditionally, UNIX domain sockets can be either unnamed, or bound to a filesystem pathname (marked as being of type socket).

 - can be either unnamed, or bound to a filesystem pathname
- part of the UNIX Address Family (AF_UNIX)
- Socket is nothing but a file in UNIX operating system

Valid socket types in the UNIX domain are: ￼￼SOCK_STREAM￼￼, for a
stream-oriented socket; ￼￼SOCK_DGRAM￼￼, for a datagram-oriented
socket that preserves message boundaries (as on most UNIX
implementations, UNIX domain datagram sockets are always reliable
and don't reorder datagrams); and (since Linux 2.6.4)
￼￼SOCK_SEQPACKET￼￼, for a sequenced-packet socket that is connection-
oriented, preserves message boundaries, and delivers messages in
the order that they were sent.
Valid socket types in the UNIX domain are: **SOCK_STREAM**, for a
stream-oriented socket; **SOCK_DGRAM**, for a datagram-oriented
socket that preserves message boundaries (as on most UNIX
implementations, UNIX domain datagram sockets are always reliable
and don't reorder datagrams); and (since Linux 2.6.4)
**SOCK_SEQPACKET**, for a sequenced-packet socket that is connection-
oriented, preserves message boundaries, and delivers messages in
the order that they were sent.

UNIX domain sockets support passing file descriptors or process
credentials to other processes using ancillary data.

### Address format
A UNIX domain socket address is represented in the following
structure:

   struct sockaddr_un {
	   sa_family_t sun_family;               /* AF_UNIX */
	   char        sun_path[108];            /* Pathname */
   };

The _sun_family_ field always contains **AF_UNIX**.  On Linux, _sun_path_
is 108 bytes in size; see also BUGS, below.

Various systems calls (for example, [bind(2)](https://man7.org/linux/man-pages/man2/bind.2.html), [connect(2)](https://man7.org/linux/man-pages/man2/connect.2.html), and
[sendto(2)](https://man7.org/linux/man-pages/man2/sendto.2.html)) take a _sockaddr_un_ argument as input.  Some other
system calls (for example, [getsockname(2)](https://man7.org/linux/man-pages/man2/getsockname.2.html), [getpeername(2)](https://man7.org/linux/man-pages/man2/getpeername.2.html),
[recvfrom(2)](https://man7.org/linux/man-pages/man2/recvfrom.2.html), and [accept(2)](https://man7.org/linux/man-pages/man2/accept.2.html)) return an argument of this type.

Three types of address are distinguished in the _sockaddr_un_
structure:

pathname
	  a UNIX domain socket can be bound to a null-terminated
	  filesystem pathname using [bind(2)](https://man7.org/linux/man-pages/man2/bind.2.html).  When the address of a
	  pathname socket is returned (by one of the system calls
	  noted above), its length is

		  offsetof(struct sockaddr_un, sun_path) + strlen(sun_path) + 1

	  and _sun_path_ contains the null-terminated pathname.  (On
	  Linux, the above **offsetof**() expression equates to the same
	  value as _sizeof(sa_family_t)_, but some other
	  implementations include other fields before _sun_path_, so
	  the **offsetof**() expression more portably describes the size
	  of the address structure.)

	  For further details of pathname sockets, see below.

unnamed
	  A stream socket that has not been bound to a pathname
	  using [bind(2)](https://man7.org/linux/man-pages/man2/bind.2.html) has no name.  Likewise, the two sockets
	  created by [socketpair(2)](https://man7.org/linux/man-pages/man2/socketpair.2.html) are unnamed.  When the address of
	  an unnamed socket is returned, its length is
	  _sizeof(sa_family_t)_, and _sun_path_ should not be inspected.

abstract
	  an abstract socket address is distinguished (from a
	  pathname socket) by the fact that _sun_path[0]_ is a null
	  byte ('\0').  The socket's address in this namespace is
	  given by the additional bytes in _sun_path_ that are covered
	  by the specified length of the address structure.  (Null
	  bytes in the name have no special significance.)  The name
	  has no connection with filesystem pathnames.  When the
	  address of an abstract socket is returned, the returned
	  _addrlen_ is greater than _sizeof(sa_family_t)_ (i.e., greater
	  than 2), and the name of the socket is contained in the
	  first _(addrlen - sizeof(sa_family_t))_ bytes of _sun_path_.