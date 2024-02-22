### send (syscall)
- [[li syscall]] for sending `len` bytes from the [[li virtual memory]] starting at adress `buff` from one [[li connection based socket]] (`SOCK_STREAM` and `SOCK_SEQPACKAGE`) to onther
- similar to the [[li write]] api for a general [[li file descriptor]] but more powerfull because of the additional `flags`
- specific for [[li socket]] [[li file descriptor]] (in a connected state)
- wrapper around [[li sendmsg]] 
	→ will build a `msg` struct and send it with [[li sendmsg]]

```C
int send(
	sockfd, // socket file discriptor
	buff,  // vm adress of data to write
	len,  // number of bytes to write
	flags,  // additional options
) // -> return value
```


# Anki
START
Basic
[[li send]] vs [[li write]] [[li syscall]]
- what are they used for 
- similarities
- differences

Back: 
- [[li write]] is the more general api for all kinds for [[li file descriptor]]
- [[li send]] is a specific api for for [[li connection based socket]] (`SOCK_STREAM` and `SOCK_SEQPACKET`) to send over a established connection
- [[li send]] provides more options by accpeting `flags`


#### send (syscall)
- [[li syscall]] for sending `len` bytes from the [[li virtual memory]] starting at adress `buff` from one [[li connection based socket]] (`SOCK_STREAM` and `SOCK_SEQPACKAGE`) to onther
- similar to the [[li write]] api for a general [[li file descriptor]] but more powerfull because of the additional `flags`
- specific for [[li socket]] [[li file descriptor]] (in a connected state)
- wrapper around [[li sendmsg]] 
	→ will build a `msg` struct and send it with [[li sendmsg]]

```C
int send(
	sockfd, // socket file discriptor
	buff,  // vm adress of data to write
	len,  // number of bytes to write
	flags,  // additional options
) // -> return value
```

#### write (syscall)
- [[li syscall]] for writing `count` bytes to a [[li file descriptor]] from the [[li virtual memory]] starting at adress `buff`
```C
int write(
	count, // number of bytes
	buff,  // vm adress of data to write
)
```

#### [[li file descriptor]]
- [[li file descriptor]] unique identifier for any kind of data stream
	- `CHR`: character special file(special part of the file system e.g. for a device or [[li standard streams]]) 
	- `DIR`: opend directory
	- `unix`: unix domain socket ([[li unix domain socket]])
	- `REG`: regular [[li file|file]]
	- `IPv4/IPv6`: internet domain socket [[li internet domain socket]]
	- `FIFO`: [[li FIFO special file]]
→ same interface 
- opening modes:
	- `r`: read only
	- `w`: write only
	- `u`: read and write
- index (small integer) to an entry in the [[li process]] table of open [[li file descriptor|file descriptors]]

Tags: code linux
<!--ID: 1708606367187-->
END

