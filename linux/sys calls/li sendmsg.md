### sendmsg (syscall)
- [[li syscall]] for sending a message sturct from one [[li socket]] to another 
- the messagt struct `msg` is containing aditional information like desination adress and frags 
- for [[li connection based socket]] in a connected state or [[li conection less socket]]
- underlaying functions of [[li send]] and [[li sendto]]
	→ [[li send]] and [[li sendto]] will just create the `msg` struct based on the given adress ang flags 

```C
int send(
	sockfd, // socket file discriptor
	msg,  // msg struct
	flags,  // frags for additional options
) // -> return value
```

```C
struct msghdr {
   void         *msg_name;       /* Optional address */
   socklen_t     msg_namelen;    /* Size of address */
   struct iovec *msg_iov;        /* Scatter/gather array */
   size_t        msg_iovlen;     /* # elements in msg_iov */
   void         *msg_control;    /* Ancillary data, see below */
   size_t        msg_controllen; /* Ancillary data buffer len */
   int           msg_flags;      /* Flags (unused) */
}
```


# Anki
START
Basic
[[li send]] vs [[li sendto]] [[li syscall]]

Back: 
- send is used mainly for [[li connection based socket]] (`SOCK_STREAM` and `SOCK_SEQPACKET`) to send over a established connection
- [[li sendmsg]] can be used for [[li connection based socket]] or [[li conection less socket]]
- [[li sendmsg]] sends a `msg` struct containing `dest_adress` and `flags` and is the uderlaying function used by [[li send]] and [[li sendto]]

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

### sendmsg (syscall)
- [[li syscall]] for sending a message sturct from one [[li socket]] to another 
- the messagt struct `msg` is containing aditional information like desination adress and frags 
- for [[li connection based socket]] in a connected state or [[li conection less socket]]
- underlaying functions of [[li send]] and [[li sendto]]
	→ [[li send]] and [[li sendto]] will just create the `msg` struct based on the given adress ang flags 

```C
int send(
	sockfd, // socket file discriptor
	msg,  // msg struct
	flags,  // frags for additional options
) // -> return value
```

```C
struct msghdr {
   void         *msg_name;       /* Optional address */
   socklen_t     msg_namelen;    /* Size of address */
   struct iovec *msg_iov;        /* Scatter/gather array */
   size_t        msg_iovlen;     /* # elements in msg_iov */
   void         *msg_control;    /* Ancillary data, see below */
   size_t        msg_controllen; /* Ancillary data buffer len */
   int           msg_flags;      /* Flags (unused) */
}
```

Tags: code linux
<!--ID: 1708606367180-->
END