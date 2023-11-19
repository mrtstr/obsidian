## [[li fork|fork]]
- [[linux]] [[li syscall]] for creating a new [[li process]] from a [[li parent process]] by duplicating the calling [[li parent process]]
- the newly created [[li child process]] has its own [[li process id]] and a separate [[li memory]] spaces but with the same conent
- `fork()` will return the [[li process id]] of the [[li child process]]
- every [[li process]] knows its [[li parent process]] [[li process id]] `PPID`
- often used as [[li fork–exec]] combination where the [[li process]] clones itself and overwrites the [[li process image]] with other instructions

# Anki

START
Basic
### [[li fork|fork]]
- concept
- how its often used
Back: 

- [[linux]] [[li syscall]] for creating a new [[li process]] from a [[li parent process]] by duplicating the calling [[li parent process]]
- the newly created [[li child process]] has its own [[li process id]] and a separate [[li memory]] spaces but with the same conent
- `fork()` will return the [[li process id]] of the [[li child process]]
- every [[li process]] knows its [[li parent process]] [[li process id]] `PPID`

Tags: code linux
<!--ID: 1700385886834-->
END