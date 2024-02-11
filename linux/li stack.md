## [[li stack]]
- segment inside the [[li process image]] in the [[li virtual memory]] space of a [[li process]]
- execution memory of a [[li thread]] → a [[li process]] can have multiple [[li stack|stacks]]
- Fixed size (set when the [[li thread]] is created)
- contains 
	- local variables
	- function arguments
	- control information (e.g. adress pointers)
	- including return addresses'
- lifetime of data is limited to the end of the scope

#### [[li stack]] management
- manages by the [[li memory management unit]] of the [[li kernel]]
- LIFO (Last-In-First-Out) data structure
- when a function is called the stack grows and when the function is exited everything is removed except the reurn values (stack pointer set back to the possion of the function start)

### stack pointer 
is a small register that stores the memory address of the last data element added to the  [[li stack]]

## relevant
![[li process image#li process image process image summary]]

# anki

START
Basic
## [[li stack]]
- concept
- size
- management

Back: 
## [[li stack]]
- segment inside the [[li process image]] in the [[li virtual memory]] space of a [[li process]]
- execution memory of a [[li thread]] → a [[li process]] can have multiple [[li stack|stacks]]
- Fixed size (set when the [[li thread]] is created)
- contains 
	- local variables
	- function arguments
	- control information (e.g. adress pointers)
	- including return addresses'
- lifetime of data is limited to the end of the scope

#### [[li stack]] management
- manages by the [[li memory management unit]] of the [[li kernel]]
- LIFO (Last-In-First-Out) data structure
- when a function is called the stack grows and when the function is exited everything is removed except the reurn values (stack pointer set back to the possion of the function start)

### stack pointer 
is a small register that stores the memory address of the last data element added to the  [[li stack]]

### [[li process image|process image summary]]
- a [[li process]] has its own [[li virtual memory]] space
- the [[li virtual memory]] space consists of 4 parts
	- [[li stack]]: for local (in scope) variables 
	- [[li heap]]: for manuel dynamicly allocated and deleted data
	- [[li data segment]]: for static/global variables that are 
	- [[li code segment]]: for the binary code that is executed ([[li program counter]] of each [[li thread]] keeping track of the location)

![[Program_memory_layout.pdf 5.jpg]]
Tags: code linux
<!--ID: 1701528585799-->
END