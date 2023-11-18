## [[li fork|fork]]
- [[li fork]] creates a new [[li process]] by duplicating the calling [[li process]]
	→ child process and the parent [[li process]] run in separate [[li memory]] spaces but  both [[li memory]] spaces have the same content
- returns the `PID` if the child [[li process]]



the stack, the heap, but also the file descriptors meaning **the standard input, the standard output and the standard error.**

It means that if my parent process was writing to the current shell console, the child process will also write to the shell console.

The execution of the cloned process will also start **at the same instruction as the parent process.**



Nicht kopiert wird hingegen das Textsegment, das von beiden Prozessen gleichermaßen benutzt wird. 
Beide Prozesse arbeiten mit unterschiedlichen Befehlszeigern.