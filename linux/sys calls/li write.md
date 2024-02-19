
### write (syscall)
- [[li syscall]] for writing `count` bytes to a [[li file descriptor]] from the [[li virtual memory]] starting at adress `buff`
```C
int write(
	count, // number of bytes
	buff,  // vm adress of data to write
)
```