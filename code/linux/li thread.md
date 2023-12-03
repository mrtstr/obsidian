

The second note: All threads running in the process share all resources of the process.
we can say that each thread has its own part of address space logically assigned to him, but physically accessible to everybody in the process, but each thread has its own private stack pointer.

thread is a flow of execution through the process code, with its own program counter that keeps track of which instruction to execute next,
system registers which hold its current working variables, and a stack which contains the execution history.

A thread shares with its peer threads few information like code segment, data segment and open files. When one thread alters a code segment memory item, all other threads see that.
Here are some differences between a process and a thread:

1.  A process is an independent program or application that runs in its own address space, while a thread is a unit of execution within a process that shares the same address space as the process.
2.  Each process has its own virtual memory space, while threads share the same virtual memory space. This means that each process has its own copy of the program code and data, while threads share the same copy of the program code and data.
3.  Processes are more heavyweight than threads, meaning that they require more resources to run. Threads are more lightweight and can be created and destroyed more quickly than processes.
4.  Each process has its own set of system resources, such as file descriptors and network sockets, while threads share the same set of system resources.
5.  Processes are generally more isolated from each other than threads. If one process crashes, it does not affect other processes. However, if one thread crashes, it can potentially affect other threads within the same process.

Here is an example to illustrate the difference between a process and a thread:

Suppose you have a web browser application running on your computer. The browser is a process that has multiple tabs open. Each tab is a separate thread within the process. The browser process provides the environment for the tabs to run and manages the shared resources, such as network sockets and memory. Each tab thread can run concurrently and perform different tasks, such as loading web pages or executing scripts. If one tab crashes, it does not affect the other tabs, but if the browser process crashes, all the tabs will be closed.

In summary, a process is an independent program that runs in its own address space, while a thread is a unit of execution within a process that shares the same address space as the process. Threads are more lightweight than processes and can run concurrently within the same process. Processes are more isolated from each other than threads, and each process has its own set of system resources.

There is a misconception behind this question that is caused by terminology - every process needs a thread or it will never run. In any operating system, every application - system software or user - needs two things - at least one process and at least one thread. The process - in terms of a process control block (PCB) - defines the physical resources - such as disk space, memory allocation, heap size, stack size, etc. The thread is what is scheduled by the OS scheduler - in other words, it decides when an application runs, or is paused, or is waiting for a resource, etc. The confusion comes about when we talk about multi-threaded processes. In these situations, each thread is often regarded as a lightweight process (LWP) which means it keeps track of its own set of registers, memory pointers, etc but will share other objects such as file allocations and other resources. There are benefits to multi-threading even on single processor systems because if part of an application is paused (waiting for data from disk, for example) another thread can run - which may be another thread in the same application. Obviously, on a multi-core or multi-processor system, multi-threaded applications can run faster because multiple threads can run on multiple cores simultaneously. However, this is not as straightforward as it sounds because there are still issues with resource access that may limit which threads can execute simultaneously. There is also an overhead associated with switching between threads - the so-called context switch. If you switch processes you will generally need to reload all the processor registers, memory pointers, possibly even loading data from swap or equivalent. The benefit of LWP is that because some resources are shared you may not need to reload everything, reducing the context switch overhead. How big a problem this is depends on the underlying CPU and computer architecture.

https://en.wikipedia.org/wiki/Process_control_block

All global variables, heap storage and code are shared. Basically, the settings for the MMU will be identical [1] for all threads in a process - they can all access all the same memory. The register values are different (particularly the stack pointer will ALWAYS be different in each thread - something has gone very wrong if two threads use the same stack memory). Any register outside of the stack-pointer register can be the same or different, depending on what is being worked on.

Note that all of the stack memory IS available to all threads, so one thread that has a local variable, can take the address of that variable and pass it to another thread, and the other thread can for example read data from a file into the variable, and then wake the original thread saying “done that now”.

[1] probably so far that ALL threads use the exact same address for the MMU page-tables, within that process, regardless of which thread is actually running and which processor it is being run on. Each processor core has it’s own MMU page table register - CR3 in x86, other names in other processors - and it gets loaded only when the processor is told to run a different process, but if your one process has a dozen threads, the OS can switch between any of those threads without changing the page-table register.
A _**thread**_ is a basic unit of CPU utilization, consisting of a program counter, a stack, and a set of registers, ( and a thread ID. )

#### 4.6.1 The fork( ) and exec( ) System Calls

-   Q: If one thread forks, is the entire process copied, or is the new process single-threaded?
-   A: System dependant.
-   A: If the new process execs right away, there is no need to copy all the other threads. If it doesn't, then the entire process should be copied.
-   A: Many versions of UNIX provide multiple versions of the fork call for this purpose.

#### 4.6.2 Signal Handling

-   Q: When a multi-threaded process receives a signal, to what thread should that signal be delivered?
-   A: There are four major options:
    1.  Deliver the signal to the thread to which the signal applies.
    2.  Deliver the signal to every thread in the process.
    3.  Deliver the signal to certain threads in the process.
    4.  Assign a specific thread to receive all signals in a process.
-   The best choice may depend on which specific signal is involved.
-   UNIX allows individual threads to indicate which signals they are accepting and which they are ignoring. However the signal can only be delivered to one thread, which is generally the first thread that is accepting that particular signal.
-   UNIX provides two separate system calls, kill( pid, signal ) and pthread_kill( tid, signal ), for delivering signals to processes or specific threads respectively.
-   Windows does not support signals, but they can be emulated using Asynchronous Procedure Calls ( APCs ). APCs are delivered to specific threads, not processes.

#### 4.6.3 Thread Cancellation

-   Threads that are no longer needed may be cancelled by another thread in one of two ways:
    1.  **Asynchronous Cancellation** cancels the thread immediately.
    2.  **Deferred Cancellation** sets a flag indicating the thread should cancel itself when it is convenient. It is then up to the cancelled thread to check this flag periodically and exit nicely when it sees the flag set.
-   ( Shared ) resource allocation and inter-thread data transfers can be problematic with asynchronous cancellation.
#### 4.7.2 Linux Threads

-   Linux does not distinguish between processes and threads - It uses the more generic term "tasks".
-   The traditional fork( ) system call completely duplicates a process ( task ), as described earlier.
-   An alternative system call, clone( ) allows for varying degrees of sharing between the parent and child tasks, controlled by flags such as those shown in the following table:

>  
> 
> flag
> 
> Meaning
> 
> CLONE_FS
> 
> File-system information is shared
> 
> CLONE_VM
> 
> The same memory space is shared
> 
> CLONE_SIGHAND
> 
> Signal handlers are shared
> 
> CLONE_FILES
> 
> The set of open files is shared

-   Calling clone( )with no flags set is equivalent to fork( ). Calling clone( ) with CLONE_FS, CLONE_VM, CLONE_SIGHAND, and CLONE_FILES is equivalent to creating a thread, as all of these data structures will be shared.
-   Linux implements this using a structure task_struct, which essentially provides a level of indirection to task resources. When the flags are not set, then the resources pointed to by the structure are copied, but if the flags are set, then only the pointers to the resources are copied, and hence the resources are shared. ( Think of a deep copy versus a shallow copy in OO programming. )
-   **( Removed from 9th edition )** Several distributions of Linux now support the NPTL ( Native POXIS Thread Library )
    -   POSIX compliant.
    -   Support for SMP ( symmetric multiprocessing ), NUMA ( non-uniform memory access ), and multicore processors.
    -   Support for hundreds to thousands of threads.

## [[li thread]]
- unit of execution within a [[li process]] 
- A thread is a flow of execution through the process code
- has a sequence of instructions that can be [[li scheduling|scheduled]] for execution independently by the [[li kernel]]
- haave access to the same memory (even though they have their own stack and stack pointer they could access the stack of other threads)
- [[li process]] can have multiple [[li thread]] which work on tasks independently 
- [[li thread|threads]] share the [[li virtual memory]] space of the [[li process]] they belong to but have their own [[li stack]] within that [[li virtual memory]] space
- private stack pointer, 
- private program counter that keeps track of which instruction to execute next
- thread represents a separate flow of control
- system registers which hold its current working variables
- stack which contains the execution history.


1.  [[li program counter]] to keep track of which instruction to execute next.
2.  Registers: hold current working variables.
3.  [[li stack]] and stack pointer: contains execution history.

The information such as [[li code segment]], [[li data segment]] and open files are shared between peer threads. 
When one thread alters a code segment memory item, all other threads see that.

![[0 _MHahkou-coeq5Py.webp]]

## [[li thread]] commands
-   PID: Unique process identifier
-   LWP: Unique thread identifier inside a process
-   NLWP: Number of threads for a given process
```sh
ps -efL # NLWP iz the number of threads of the process
```

