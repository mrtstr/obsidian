
- combination of [[li fork]]/[[li clone]] and [[li exec]] is often used for creating [[li child process]] that is executing some [[li executable binary file]]
	→ first create a new [[li process]] with the same [[li process image]] using [[li fork]] but then replace it with some [[li executable binary file]] using [[li exec]]
- Unesseary memory writen is prevented by [[li memory paging|copy on write]] performed by the [[li virtual memory]] management





-   There are two options for the parent process after creating the child:
    1.  Wait for the child process to terminate before proceeding. 
    2. The parent makes a wait( ) system call, for either a specific child or for any child, which causes the parent process to block until the wait( ) returns.
    3. UNIX shells normally wait for their children to complete before issuing a new prompt.

    5.  Run concurrently with the child, continuing to process without waiting. This is the operation seen when a UNIX shell runs a process as a background task. It is also possible for the parent to run for a while, and then wait for the child later, which might occur in a sort of a parallel processing operation. ( E.g. the parent may fork off a number of children without waiting for any of them, then do a little work of its own, and then wait for the children. )
-   Two possibilities for the address space of the child relative to the parent:
    1.  The child may be an exact duplicate of the parent, sharing the same program and data segments in memory. Each will have their own PCB, including program counter, registers, and PID. This is the behavior of the **fork** system call in UNIX.
    2.  The child process may have a new program loaded into its address space, with all new code and data segments. This is the behavior of the **spawn** system calls in Windows. UNIX systems implement this as a second step, using the **exec** system call.






![[Process.png]]


## [[li process creation|process creation]]

## relveant

![[li process image#li process image process image summary]]

![[li fork#li fork fork]]

![[li exec#li exec exec]]


![[li memory paging#copy on write]]
