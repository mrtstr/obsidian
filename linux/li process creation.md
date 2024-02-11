
### [[li process creation]]
- combination of [[li fork]]/[[li clone]] and [[li exec]] is often used for creating [[li child process]] that is executing some [[li executable binary file]]
	→ first create a new [[li process]] with the same [[li process image]] using [[li fork]] but then replace it with some [[li executable binary file]] using [[li exec]]
- Unesseary memory writen is prevented by [[li memory paging|copy on write]] performed by the [[li virtual memory]] management

![[Process.png]]

### Sqauentially or parallel 
- the parent can either use the [[li syscall]] [[li wait]] to wait untill the [[li child process]] [[li process termination|terminated]] (e.g. running a command in a [[li shell]])
- or the [[li parent process]] can continue to run in parallel to the [[li child process]] (e.g. running a [[li shell command]] in the background)





## [[li process creation|process creation]]

## relveant

![[li process image#li process image process image summary]]

![[li fork#li fork fork]]

![[li exec#li exec exec]]

![[li clone#li clone]]

![[li wait#li wait wait]]

![[li copy on write#li copy on write copy on write]]

# Anki

START
Basic
[[li process creation]]
- summary
- what does the [[li parent process]] do after the [[li child process]] is started
- 4 involved [[li syscall]]
- what concept does prevent unnessary memory coping when creating a new [[li process]]
Back: 
### [[li process creation]]
- combination of [[li fork]]/[[li clone]] and [[li exec]] is often used for creating [[li child process]] that is executing some [[li executable binary file]]
	→ first create a new [[li process]] with the same [[li process image]] using [[li fork]] but then replace it with some [[li executable binary file]] using [[li exec]]
- Unesseary memory writen is prevented by [[li memory paging|copy on write]] performed by the [[li virtual memory]] management


### sqeuentially or parallel 
- the parent can either use the [[li syscall]] [[li wait]] to wait untill the [[li child process]] [[li process termination|terminated]] (e.g. running a command in a [[li shell]])
- or the [[li parent process]] can continue to run in parallel to the [[li child process]] (e.g. running a [[li shell command]] in the background)


### [[li process image|process image summary]]
- a [[li process]] has its own [[li virtual memory]] space
- the [[li virtual memory]] space consists of 4 parts
	- [[li stack]]: for local (in scope) variables 
	- [[li heap]]: for manuel dynamicly allocated and deleted data
	- [[li data segment]]: for static/global variables that are 
	- [[li code segment]]: for the binary code that is executed ([[li program counter]] of each [[li thread]] keeping track of the location)

## relevant [[li syscall]]
### [[li fork|fork]]
- [[li syscall]] for creating a new [[li child process]] from a [[li parent process]] with the same [[li process image]] as the [[li parent process]] 
- the newly created [[li child process]] has its own [[li process id]] and a separate [[li virtual memory]] spaces but with the same conent ([[li process image]])
- the `fork()` function will return the [[li process id]] of the newly created [[li child process]]
- often used in combination with [[li exec]] for [[li process creation]]
	→ first create a new [[li process]] with the same [[li process image]] but then replace it with something else 
- the [[li syscall]] [[li clone]] can do the same but gives more freedom about which resources are shared with the child [[li process]] which maked it possipble to create [[li thread]]

### [[li exec|exec]]
- [[li syscall]] `exec` will replace the [[li process image]] of the [[li process]] with an [[li executable binary file]]
	→ [[li process id|PID]] if the [[li process]] does not change but the machine code in the [[li code segment]] and the data in [[li stack]], [[li data segment]] and [[li heap]] is replaced with another programm
- often used in combination with [[li fork]] (or [[li clone]]) for [[li process creation]]
	→ first create a new [[li process]] with the same [[li process image]] but then replace it with something else 

### [[li clone]]
- The [[li clone]] [[li syscall]] is an upgraded version of the [[li fork]] call.
- [[linux]] [[li syscall]] for creating a new [[li process]] from a [[li parent process]] by duplicating the calling [[li parent process]] but gives more precise control over the data shared between the parent and child [[li process|processes]]
- used for creating [[li process]] or [[li thread]]

### flags
- `CLONE_FS`    File-system information is shared
- `CLONE_VM`    The same memory space is shared
- `CLONE_SIGHAND` Signal handlers are shared
- `CLONE_FILES` The set of open files is shared

### [[li wait|wait]]
-  [[linux]] [[li syscall]]
- `wait <pid>` will wait untill a [[li job|background]] [[li process]] is terminated and will return its [[li return code]]

## [[li copy on write|copy on write]]
- [[li memory management]] concept for sharing [[li physical memory (RAM)]] between [[li process|processes]] untill one of the involved [[li process]] performs a wirte operation
- a write operation the pysical memory will be copyed and changed
- only impacts the mapping between a [[li virtual memory]] andress and the [[li physical memory (RAM)]] adress
- from the process perspective its looks like each process has its own memory
- make [[li fork]] [[li syscall]] much more efficient

Tags: code linux
<!--ID: 1702578315623-->
END