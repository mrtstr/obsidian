### recvmsg (syscall)
- [[li syscall]] for reciving a message sturct in one [[li socket]] that was sent by another 
- the messagt struct `msg` is containing aditional information like desination adress and frags 
- for [[li connection based socket]] in a connected state or [[li conection less socket]]
- underlaying functions of [[li recv]] and [[li recvfrom]]
	→ [[li recv]] and [[li recvfrom]] will just create the `msg` struct based after reciving the data

```C
int recvmsg(
	sockfd, // socket file discriptor
	msg,  // msg struct
	flags,  // frags for additional options
)
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