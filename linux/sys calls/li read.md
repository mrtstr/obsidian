### read (syscall)
- [[li syscall]] for reading `count` bytes from a [[li file descriptor]] and writing it to the [[li virtual memory]] starting at adress `buff`
```C
int read(
	count, 
	buff,
) // -> return code
```