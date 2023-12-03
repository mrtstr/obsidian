- unesseary memory writen is prevented by [[li memory paging|copy on write]] performed by the [[li virtual memory]] management
![[li memory paging#copy on write]]

![[li fork#li fork fork]]

![[li exec#li exec exec]]

combination of [[li fork]] and [[li exec]] is often used creating and child [[li process]] that is executing something

In the kernel, fork is actually implemented by a `clone` system call. This `clone` interfaces effectively provides a level of abstraction in how the Linux kernel can create processes.

`clone` allows you to explicitly specify which parts of the new process are copied into the new process, and which parts are shared between the two processes. This may seem a bit strange at first, but allows us to easily implement _threads_ with one very simple interface.

- child process** is started by parent process
- Processes may create other processes through appropriate system calls, such as **fork** or **spawn**
- When linux starts, it runs a single program, **init** with PID 1 (prime ancestor of all processes)
other system processes are started by **init** or by other processes started by **init**
-   There are two options for the parent process after creating the child:
    1.  Wait for the child process to terminate before proceeding. The parent makes a wait( ) system call, for either a specific child or for any child, which causes the parent process to block until the wait( ) returns. UNIX shells normally wait for their children to complete before issuing a new prompt.
    2.  Run concurrently with the child, continuing to process without waiting. This is the operation seen when a UNIX shell runs a process as a background task. It is also possible for the parent to run for a while, and then wait for the child later, which might occur in a sort of a parallel processing operation. ( E.g. the parent may fork off a number of children without waiting for any of them, then do a little work of its own, and then wait for the children. )
-   Two possibilities for the address space of the child relative to the parent:
    1.  The child may be an exact duplicate of the parent, sharing the same program and data segments in memory. Each will have their own PCB, including program counter, registers, and PID. This is the behavior of the **fork** system call in UNIX.
    2.  The child process may have a new program loaded into its address space, with all new code and data segments. This is the behavior of the **spawn** system calls in Windows. UNIX systems implement this as a second step, using the **exec** system call.
own programs with the system calls **fork()**, **exec()**, and **wait()**.
Related man pages:

-   [fork( 2 )](http://linuxmanpages.com/man2/fork.2.php)
-   [exec( 3 )](http://linuxmanpages.com/man3/exec.3.php)
-   [wait( 2 )](http://linuxmanpages.com/man2/wait.2.php)

As we already stated, processes are **managed by the Kernel** on Linux.

when you boot a Linux system, your Linux kernel is loaded into memory, it is given a virtual filesystem in the RAM (also called **initramfs**) and the initial commands are executed.



![[Process.png]]

