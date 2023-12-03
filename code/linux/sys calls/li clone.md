![[li fork#li fork fork]]

## [[li clone]]
- The [[li clone]] [[li syscall]] is an upgraded version of the [[li fork]] call.
- [[linux]] [[li syscall]] for creating a new [[li process]] from a [[li parent process]] by duplicating the calling [[li parent process]] but gives more precise control over the data shared between the parent and child [[li process|processes]]
- used for creating [[li process]] or [[li thread]]

### flags
- `CLONE_FS`    File-system information is shared
- `CLONE_VM`    The same memory space is shared
- `CLONE_SIGHAND` Signal handlers are shared
- `CLONE_FILES` The set of open files is shared


# Anki

START
Basic
[[li clone]]
- concept
- difference to [[li fork]]
- flags (4)
Back: 
## [[li clone]]
- The [[li clone]] [[li syscall]] is an upgraded version of the [[li fork]] call.
- [[linux]] [[li syscall]] for creating a new [[li process]] from a [[li parent process]] by duplicating the calling [[li parent process]] but gives more precise control over the data shared between the parent and child [[li process|processes]]

### flags
- `CLONE_FS`    File-system information is shared
- `CLONE_VM`    The same memory space is shared
- `CLONE_SIGHAND` Signal handlers are shared
- `CLONE_FILES` The set of open files is shared


## [[li fork|fork]]
- [[linux]] [[li syscall]] for creating a new [[li process]] from a [[li parent process]] by duplicating the calling [[li parent process]]
- the newly created [[li child process]] has its own [[li process id]] and a separate [[li virtual memory]] spaces but with the same conent
- `fork()` will return the [[li process id]] of the [[li child process]]
- every [[li process]] knows its [[li parent process]] [[li process id]] `PPID`
- often used as [[li fork–exec]] combination where the [[li process]] clones itself and overwrites the [[li process image]] with other instructions
- unesseary memory writen is prevented by [[li memory paging|copy on write]] performed by the [[li virtual memory]] management


Tags: code linux
<!--ID: 1701613701250-->
END