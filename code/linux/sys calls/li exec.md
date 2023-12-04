## [[li exec|exec]]
- [[li syscall]] `exec` will replace the [[li process image]] of the [[li process]] with an [[li executable binary file]]
	→ [[li process id|PID]] if the [[li process]] does not change but the machine code in the [[li code segment]] and the data in [[li stack]], [[li data segment]] and [[li heap]] is replaced with another programm
- often used in combination with [[li fork]] (or [[li clone]]) for [[li process creation]]
	→ first create a new [[li process]] with the same [[li process image]] but then replace it with something else 

## relevant
![[li process image#li process image process image summary]]

![[li fork#li fork fork]]

### example `exec ls`
execute `exec ls` command in your [[li bash]] [[li terminal]]
->  [[li shell]] will terminate as soon as the command is completed because the [[li process image]] ([[li bash]] interpreter) is repalced


# Anki

START
Basic
[[li exec]]
- concept
- how is it often used
- what happens when its called in a [[li terminal]]
Back: 
## [[li exec|exec]]
- [[li syscall]] `exec` will replace the [[li process image]] of the [[li process]] with an [[li executable binary file]]
	→ [[li process id|PID]] if the [[li process]] does not change but the machine code in the [[li code segment]] and the data in [[li stack]], [[li data segment]] and [[li heap]] is replaced with another programm
- often used in combination with [[li fork]] (or [[li clone]]) for [[li process creation]]
	→ first create a new [[li process]] with the same [[li process image]] but then replace it with something else 

### example `exec ls`
execute `exec ls` command in your [[li bash]] [[li terminal]]
->  [[li shell]] will terminate as soon as the command is completed because the [[li process image]] ([[li bash]] interpreter) is repalced

### [[li process image|process image summary]]
- a [[li process]] has its own [[li virtual memory]] space
- the [[li virtual memory]] space consists of 4 parts
	- [[li stack]]: for local (in scope) variables 
	- [[li heap]]: for manuel dynamicly allocated and deleted data
	- [[li data segment]]: for static/global variables that are 
	- [[li code segment]]: for the binary code that is executed ([[li program counter]] of each [[li thread]] keeping track of the location)

## [[li fork|fork]]
- [[li syscall]] for creating a new [[li child process]] from a [[li parent process]] with the same [[li process image]] as the [[li parent process]] 
- the newly created [[li child process]] has its own [[li process id]] and a separate [[li virtual memory]] spaces but with the same conent ([[li process image]])
- the `fork()` function will return the [[li process id]] of the newly created [[li child process]]

Tags: code linux
<!--ID: 1701619491883-->
END