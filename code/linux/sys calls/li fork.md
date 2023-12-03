## [[li fork|fork]]
- [[linux]] [[li syscall]] for creating a new [[li process]] from a [[li parent process]] by duplicating the calling [[li parent process]]
- the newly created [[li child process]] has its own [[li process id]] and a separate [[li virtual memory]] spaces but with the same conent
- `fork()` will return the [[li process id]] of the [[li child process]]
- every [[li process]] knows its [[li parent process]] [[li process id]] `PPID`
- often used as [[li fork–exec]] combination where the [[li process]] clones itself and overwrites the [[li process image]] with other instructions
- unesseary memory writen is prevented by [[li memory paging|copy on write]] performed by the [[li virtual memory]] management

## copy on write
![[li memory paging#copy on write]]]



# Anki

START
Basic
### [[li fork|fork]]
- concept
- how its often used
Back: 
## [[li fork|fork]]
- [[linux]] [[li syscall]] for creating a new [[li process]] from a [[li parent process]] by duplicating the calling [[li parent process]]
- the newly created [[li child process]] has its own [[li process id]] and a separate [[li virtual memory]] spaces but with the same conent
- `fork()` will return the [[li process id]] of the [[li child process]]
- every [[li process]] knows its [[li parent process]] [[li process id]] `PPID`
- often used as [[li fork–exec]] combination where the [[li process]] clones itself and overwrites the [[li process image]] with other instructions
- unesseary memory writen is prevented by [[li memory paging|copy on write]] performed by the [[li virtual memory]] management

## copy on write
- [[li memory management]] concept for sharing [[li physical memory (RAM)]] between [[li process|processes]] untill one of the involved [[li process]] performs a wirte operation
- a write operation the pysical memory will be copyed and changed
- only impacts the mapping between a [[li virtual memory]] andress and the [[li physical memory (RAM)]] adress
- from the process perspective its looks like each process has its own memory
- make [[li fork]] [[li syscall]] much more efficient
![[1 B3jzse_G1dIwL5US0LlStg 3.webp]]
Tags: code linux
<!--ID: 1700385886834-->
END