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
