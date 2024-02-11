
## [[li process table|process table]]
- maintained by the [[li kernel]]
- arry that contains the [[li process control block|process control blocks]] for all of the current [[li process|processes]] in the system

![[li process control block#li process control block process control block]]


# Anki

START
Basic
differnce [[li process control block]] and [[li process table]]
Back: 
## [[li process table|process table]]
- maintained by the [[li kernel]]
- arry that contains the [[li process control block|process control blocks]] for all of the current [[li process|processes]] in the system

## [[li process control block|process control block]]
- data structure used by the [[li kernel]] to store all the information about a [[li process]]
###  contains
- [[li state]]
- [[li process id]]
- [[li parent process]]
- [[li child process]] (their [[li process id]])
- [[li virtual memory]]
- [[li thread|threads]] and controll information ([[li program counter]], [[li cpu register]], [[li scheduling]] information)
- **Accounting information** - 
	- user
	- Command used to activate the process.
	- CPU time consumed
- **I/O information** - 
	- Devices allocated
	- open [[li file]]
	- [[li standard streams]]
Tags: code linux
<!--ID: 1702578315599-->
END