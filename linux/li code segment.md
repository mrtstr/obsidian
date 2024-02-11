## [[li code segment|code segment]]
- segment inside the [[li process image]] in the [[li virtual memory]] space of a [[li process]]
- contains executable binary code (mapped from the [[li disc]] to the [[li virtual memory]] of the [[li process]])
- [[li program counter]] of a [[li thread]] points to the current location in the [[li code segment]] of eachexecution flow
- read only 
## relevant

![[li process image#li process image process image summary]]

![[li program counter#program counter]]

# anki

START
Basic
instruction segment (3)
Back: 
- segment inside the [[li process image]] in the [[li virtual memory]] space of a [[li process]]
- contains executable binary code (mapped from the [[li disc]] to the [[li virtual memory]] of the [[li process]])
- [[li program counter]] of a [[li thread]] points to the current location in the [[li code segment]] of eachexecution flow
- read only 

### [[li process image|process image summary]]
- a [[li process]] has its own [[li virtual memory]] space
- the [[li virtual memory]] space consists of 4 parts
	- [[li stack]]: for local (in scope) variables 
	- [[li heap]]: for manuel dynamicly allocated and deleted data
	- [[li data segment]]: for static/global variables that are 
	- [[li code segment]]: for the binary code that is executed ([[li program counter]] of each [[li thread]] keeping track of the location)

### [[li program counter|program counter]]
- Contains the [[li virtual memory]] address of the instruction in the [[li code segment]] that's currently executing
- each [[li thread]] has its own [[li program counter]] pointing to different adresses in the shared [[li code segment]] (of the [[li process]])


![[Program_memory_layout.pdf 2.jpg]]

Tags: code linux
<!--ID: 1701528585788-->
END