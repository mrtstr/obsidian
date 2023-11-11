## `top`
- show table of runnnig [[li process]] currently being managed by the Linux kernel with properties like resources' usage
- real-time view of a running system

## information
![[li process#basic li process properties]]

![[li scheduling and CPU time#(overall) priority level (PR)]]
![[li scheduling and CPU time#niceness (NI)]]


![[li process memory#memory]]

![[li scheduling and CPU time#CPU time]]

# Anki

START
Basic
[[li process]] properties displayed in [[li top and htop]] (12)

Back: 

### basic [[li process]] properties
- **PID**: Unique Process ID given to each process.
- **User**: Username of the process owner.
- **Command**: Command used to activate the process.

### (overall) priority level (PR)
- numer in range (-100 to 39) 
- the lower the **PR** the higher the priority
- **direct** impact on the scheduling (CPU time)
- can only be directly changes with [[li root]] rights and is usually stet automaticity by the [[li kernel]]

### niceness (NI)
- used to derrive the **priority level (PR)** of normal user processes
- numer in range (-20 to 19) that can be set by a non [[li root]] user to influence the priority of the process
- hight niceness leads to a low priority
Tags: code linux

### states (S)
-   `D` = **uninterruptible sleep**: waiting for a resource to be available (will wakeup to handle signals)
-   `R` = **running**: running or it’s ready to run
-   `S` = **sleeping**: waiting for a resource to be available (will not wakeup to handle signals)
-   `T` = **traced or stopped**
-   `Z` = **zombie**: terminated child process that remains in the system's process table while waiting for its parent process to collect its exit status

### memory concumption 
- **VIRT**: virtual memory
	- size of the processes adress space
	- e.g. process memory-maps a large file, the file is actually stored on disk, but it still takes up "address space" in the process.
- **RES**: resident memory
	- Amount of physical memory used by a process.
- **SHR**: Amount of memory shared with other processes.
- **%MEM**; Percentage of RAM used by the process.

### CPU time
- on the [[li scheduling and CPU time|scheduling]] of the [[li kernel]]
	- **TIME+:** Total CPU time consumed by the process.
	- **%CPU**: Percentage of CPU used by the process.

<!--ID: 1699690123174-->
END