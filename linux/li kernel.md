## [[li kernel|linux kernel]]
- part of the operating system that runs with higher previleges 
![[kernel.png]]

- the[[li kernel]] has the following key responisbilities 
1.  [[li memory management unit|memory management]] 
	-  [[li memory paging]]: mapping the [[li virtual memory]] space to [[li physical memory (RAM)]] / [[li disc]] adresses
2.  [[li process]] management
	- administer the [[li process table]]
	- [[li process creation]]
	- [[li process termination]]
	- [[li interprocess communication]] with [[li signal]]
	- [[li scheduling]] [[li cpu]] time and [[li state]] management
3.  **Device drivers:** Act as mediator/interpreter between the hardware and [[li process|processes]]
4.  providing a API for [[li user process]] for kernel function: [[li syscall]] 
	- for creating ([[li fork]], [[li clone]]...) and termination ([[li exit]], [[li kill syscall]]...) [[li process]] 
	- for openining, reading, wrting [[li file]]

[[li kernel process]]
![[Linux_kernel_map.png]]



# Anki

START
Basic
[[li kernel]]
- concept
- key responsibilities 

Back: 
## [[li kernel|linux kernel]]
- part of the operating system that runs with higher previleges 
![[kernel 1.png]]

- the[[li kernel]] has the following key responisbilities 
1.  [[li memory management unit|memory management]] 
	-  [[li memory paging]]: mapping the [[li virtual memory]] space to [[li physical memory (RAM)]] / [[li disc]] adresses
2.  [[li process]] management
	- administer the [[li process table]]
	- [[li process creation]]
	- [[li process termination]]
	- [[li interprocess communication]] with [[li signal]]
	- [[li scheduling]] [[li cpu]] time and [[li state]] management
3.  **Device drivers:** Act as mediator/interpreter between the hardware and [[li process|processes]]
4.  providing a API for [[li user process]] for kernel function: [[li syscall]] 
	- for creating ([[li fork]], [[li clone]]...) and termination ([[li exit]], [[li kill syscall]]...) [[li process]] 
	- for openining, reading, wrting [[li file]]

![[Linux_kernel_map 1.png]]

Tags: code linux
<!--ID: 1702632209781-->
END