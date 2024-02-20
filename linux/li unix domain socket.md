## [[li unix domain socket]]
- [[li socket]] connection for [[li process|processes]] inside a single system
- for bidirectional [[li interprocess communication]] inside a system
- can be bound to a path in the filesystem or unnamed
- usualy of type `SOCK_STREAM` but others are also possible
- used like a normal [[li file descriptor]]
- implementet with two buffers (one for each direction)
	→ compariable to two [[li ordinary pipe]] (in case of unnamed sockets) or [[li FIFO special file]] (when the [[li unix domain socket]] is bound to the file system
- [[li unix domain socket]] are more flexible than [[li FIFO special file]] but some extra features can not be used with the [[li read]], [[li write]] [[li syscall]] but only with the [[li socket]] specific `send` and `recv`
	- They support passing file descriptors between processes;
	- They support packet and sequenced packet modes.



![[li socket#li socket]]