## OS thread
- flow of execution through the [[li process]] [[li code segment|code]]
- can be [[li scheduling|scheduled]] for execution independently by the [[li kernel]]
- to keep track of their execution flow they have their own
	1.  [[li program counter]] to keep track of which instruction to execute next.
	2.  [[li cpu register]] that holds current working variables
	3.  [[li stack]] and stack pointer withing the [[li process]] [[li virtual memory]] 
- [[li thread|threads]] share their [[li process|processes]] resources like
	- [[li virtual memory]] space 
		- threads have technically access to each others [[li stack|stacks]]
		- [[li heap]]
		- [[li code segment]]
		- [[li data segment]]
	- open [[li file|files]] ([[li standard streams]])

![[0 _MHahkou-coeq5Py.webp]]

 - if one thread crashes, it can potentially affect other threads

### [[li thread]] handling threads
-   PID: Unique process identifier
-   LWP (lightweight process): Unique thread identifier inside a process
-   NLWP (number of lightweight process): Number of threads for a given [[li process]]
```sh
ps -efL  # print all threads
```

### [[li thread]] creation
- can be created with the [[li syscall]] [[li clone]] (with additional flags)

![[li clone#li clone]]

### removing [[li thread]]
- [[li thread]] can only be removed from the context of the [[li process]] (by another [[li thread]])
- `pthread_kill` function can remove a [[li thread]] when called by another thread if the same [[li process]]

### [[li signal]] Handling
-  threads ca indicate which signals they are accepting and which they are ignoring 
- the signal can only be delivered to one thread, which is generally the first thread that is accepting that particular [[li signal]]
# -----------

![[li state#li state state of a li thread thread (of a li process process )]]

# anki
START
Basic
#### [[li thread]]
- concept
- difference to a [[li process]] (what are they sharing and what not)
- how to display [[li thread]], how are they identified?
-  [[li thread]] creation
- [[li thread]] deletion
- [[li signal]] handling
- [[li state]]
Back: 
## [[li thread]]
- flow of execution through the [[li process]] [[li code segment|code]]
- can be [[li scheduling|scheduled]] for execution independently by the [[li kernel]]
- to keep track of their execution flow they have their own
	1.  [[li program counter]] to keep track of which instruction to execute next.
	2.  [[li cpu register]] that holds current working variables
	3.  [[li stack]] and stack pointer withing the [[li process]] [[li virtual memory]] 
- [[li thread|threads]] share their [[li process|processes]] resources like
	- [[li virtual memory]] space 
		- threads have technically access to each others [[li stack|stacks]]
		- [[li heap]]
		- [[li code segment]]
		- [[li data segment]]
	- open [[li file|files]] ([[li standard streams]])

![[0 _MHahkou-coeq5Py 1.webp]]

## [[li state|state]] of a [[li thread|thread]] (of a [[li process|process]])
-   `D` = **uninterruptible sleep**: waiting for a resource to be available (will wakeup to handle signals)
-   `R` = **running**: running or it’s ready to run
-   `S` = **sleeping**: waiting for a resource to be available (will not wakeup to handle signals)
-   `T` = **traced or stopped**
-   `Z` = **zombie**: terminated child process that remains in the system's process table while waiting for its parent process to collect its exit status

### [[li thread]] handling threads
-   PID: Unique process identifier
-   LWP (lightweight process): Unique thread identifier inside a process
-   NLWP (number of lightweight process): Number of threads for a given [[li process]]
```sh
ps -efL  # print all threads
```

### [[li thread]] creation
- can be created with the [[li syscall]] [[li clone]] (with additional flags)

#### [[li clone]]
- The [[li clone]] [[li syscall]] is an upgraded version of the [[li fork]] call.
- [[linux]] [[li syscall]] for creating a new [[li process]] from a [[li parent process]] by duplicating the calling [[li parent process]] but gives more precise control over the data shared between the parent and child [[li process|processes]]
- used for creating [[li process]] or [[li thread]]

 flags
- `CLONE_FS`    File-system information is shared
- `CLONE_VM`    The same memory space is shared
- `CLONE_SIGHAND` Signal handlers are shared
- `CLONE_FILES` The set of open files is shared

### removing [[li thread]]
- [[li thread]] can only be removed from the context of the [[li process]] (by another [[li thread]])
- `pthread_kill` function can remove a [[li thread]] when called by another thread if the same [[li process]]

### [[li signal]] Handling
-  threads ca indicate which signals they are accepting and which they are ignoring 
- the signal can only be delivered to one thread, which is generally the first thread that is accepting that particular [[li signal]]

Tags: code linux
<!--ID: 1701613701255-->
END