## [[li process control block|process control block]]
- data structure used by the [[li kernel]] to store all the information about a [[li process]]
###  contains
- [[li process state]]
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


# Anki

START
Basic
[[li process control block|process control block]]
- concept (1)
- contains (7)
Back: 

- data structure used by the [[li kernel]] to store all the information about a [[li process]]
###  contains
- [[li process state]]
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
<!--ID: 1701586495622-->
END