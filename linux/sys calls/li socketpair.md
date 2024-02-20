### socketpair (syscall)
- [[li syscall]] for creating an already connected pair of [[li unix domain socket]]
- for communincating among [[li child process]] similar to bidirectional version of a [[li ordinary pipe]] 
- writes the two [[li file descriptor]] in `sv[0]` and `sv[1]` and returns a [[li return code]]
```C
int socketpair(
	domain,  
	type, 
	sv[2],
) // → return code
```


