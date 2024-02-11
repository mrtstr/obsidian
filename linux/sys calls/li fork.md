## [[li fork|fork]]
- [[li syscall]] for creating a new [[li child process]] from a [[li parent process]] with the same [[li process image]] as the [[li parent process]] 
- the newly created [[li child process]] has its own [[li process id]] and a separate [[li virtual memory]] spaces but with the same conent ([[li process image]])
- the `fork()` function will return the [[li process id]] of the newly created [[li child process]]
- often used in combination with [[li exec]] for [[li process creation]]
	→ first create a new [[li process]] with the same [[li process image]] but then replace it with something else 
- the [[li syscall]] [[li clone]] can do the same but gives more freedom about which resources are shared with the child [[li process]] which maked it possipble to create [[li thread]]

## relevant

![[li process image#li process image process image summary]]

![[li exec#li exec exec]]

![[li clone#li clone]]

![[li memory paging#copy on write]]

# Anki

START
Basic
### [[li fork|fork]]
- concept
- how its often used
- how is unesseary memory writing is prevented
Back: 
## [[li fork|fork]]
- [[li syscall]] for creating a new [[li child process]] from a [[li parent process]] with the same [[li process image]] as the [[li parent process]] 
- the newly created [[li child process]] has its own [[li process id]] and a separate [[li virtual memory]] spaces but with the same conent ([[li process image]])
- the `fork()` function will return the [[li process id]] of the newly created [[li child process]]
- often used in combination with [[li exec]] for [[li process creation]]
	→ first create a new [[li process]] with the same [[li process image]] but then replace it with something else 
- the [[li syscall]] [[li clone]] can do the same but gives more freedom about which resources are shared with the child [[li process]] which maked it possipble to create [[li thread]]
- unesseary memory writen is prevented by [[li memory paging|copy on write]] performed by the [[li virtual memory]] management

### [[li process image|process image summary]]
- a [[li process]] has its own [[li virtual memory]] space
- the [[li virtual memory]] space consists of 4 parts
	- [[li stack]]: for local (in scope) variables 
	- [[li heap]]: for manuel dynamicly allocated and deleted data
	- [[li data segment]]: for static/global variables that are 
	- [[li code segment]]: for the binary code that is executed ([[li program counter]] of each [[li thread]] keeping track of the location)

## [[li exec|exec]]
- [[li syscall]] `exec` will replace the [[li process image]] of the [[li process]] with an [[li executable binary file]]
	→ [[li process id|PID]] if the [[li process]] does not change but the machine code in the [[li code segment]] and the data in [[li stack]], [[li data segment]] and [[li heap]] is replaced with another programm
- often used in combination with [[li fork]] (or [[li clone]]) for [[li process creation]]
	→ first create a new [[li process]] with the same [[li process image]] but then replace it with something else 

## [[li clone]]
- The [[li clone]] [[li syscall]] is an upgraded version of the [[li fork]] call.
- [[linux]] [[li syscall]] for creating a new [[li process]] from a [[li parent process]] by duplicating the calling [[li parent process]] but gives more precise control over the data shared between the parent and child [[li process|processes]]
- used for creating [[li process]] or [[li thread]]

### flags
- `CLONE_FS`    File-system information is shared
- `CLONE_VM`    The same memory space is shared
- `CLONE_SIGHAND` Signal handlers are shared
- `CLONE_FILES` The set of open files is shared


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