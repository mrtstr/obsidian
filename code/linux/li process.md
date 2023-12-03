## [[li process]] concept
- A [[li process]] is an instance of a computer program in execution
- has a private [[li virtual memory]] space that is shared by its [[li thread|threads]] containing
	- [[li stack]]: for local (in scope) variables 
	- [[li heap]]: for manuel dynamicly allocated and deleted data
	- [[li data segment]]: for static/global variables that are 
	- [[li code segment]]: for the binary code that is executed ([[li program counter]] of each [[li thread]] keeping track of the location)
- can have multiple flows of execution ([[li thread|threads]]) that are [[li scheduling|scheduled]] independently by the [[li kernel]] but share the [[li process]] resources
- is created by a another [[li process]] ([[li parent process]]) 
- is managed by the [[li kernel]] in a data structure called [[li process control block]]

![[3_08_ProcessTree.jpg]]

![[li process control block#li process control block process control block]]




![[li process memory layout#li process memory layout process memory layout]]

## process execution

![[li thread#li thread]]

![[li scheduling#scheduling]]

## commands

![[li ps#`ps`]]

![[li top and htop#top]]

![[li kill#kill]]

![[li renice#`renice`]]


# Anki

START
Basic
[[li process]] summary (5)

Back: 
## [[li process]] concept
- A [[li process]] is an instance of a computer program in execution
- has a private [[li virtual memory]] space that is shared by its [[li thread|threads]] containing
	- [[li stack]]: for local (in scope) variables 
	- [[li heap]]: for manuel dynamicly allocated and deleted data
	- [[li data segment]]: for static/global variables that are 
	- [[li code segment]]: for the binary code that is executed ([[li program counter]] of each [[li thread]] keeping track of the location)
- can have multiple flows of execution ([[li thread|threads]]) that are [[li scheduling|scheduled]] independently by the [[li kernel]] but share the [[li process]] resources
- is created by a another [[li process]] ([[li parent process]]) 
- is managed by the [[li kernel]] in a data structure called [[li process control block]]

![[3_08_ProcessTree 1.jpg]]

![[Program_memory_layout.pdf 6.jpg]]

Tags: code linux
<!--ID: 1701613701258-->
END


START
Basic
basic [[li process]] properties (4)
Back: 

- **PID**: Unique Process ID given to each process.
- **User**: Username of the process owner.
- **S**: state of the process
- **Command**: Command used to activate the process.

Tags: code linux
<!--ID: 1699690123177-->
END


START
Basic
 [[li process]] 
 - commands to manage (2) and display (2) them
Back: 

## `ps`
print out process status of the **currently running** processes 
- `-A` or `-e` show all processes (like [[li top and htop]] but without realtime updates)
- `-T` show only processes connected to the used terminal (default)
- `-f` show more details

## `top`
- show table of runnnig [[li process]] currently being managed by the Linux kernel with properties like resources' usage
- real-time view of a running system

## `kill`
- kill a [[li process]] by sending a kill [[li signal]]
- there are different types of kill signals (most commong SIGKILL `-9`)
- usage `kill -9 [pid]`

## `renice`
Change the niceness values of a user (regular) [[li process]] or a group of user processes
`renice [value] -p [pids]` e.g.  `renice 5 -p 2 10` (change nicesness of process with pids 2 and 10 to 5)
`renice [value] -u [user]` e.g.  `renice -20 -u user1` (change the niceness of all processes of user1 to -20)

Tags: code linux
<!--ID: 1699690123180-->
END