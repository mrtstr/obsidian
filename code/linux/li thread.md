
The process has no stack and does not receive CPU time (not schedulable). In contrast, the thread is a unit of scheduling performed by OS kernel. Thread periodically receives quant of CPU time to make progress and has a stack to store temporal data (local variables and return addresses).
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

## [[li thread]]
- unit of execution within a [[li process]] 
- has a sequence of instructions that can be [[li scheduling and CPU time|scheduled]] for execution independently by the [[li kernel]]
- [[li process]] can have multiple [[li thread]] which work on tasks independently 
- [[li thread|threads]] share the [[li virtual memory]] space of the [[li process]] they belong to but have their own [[li stack]] within that [[li virtual memory]] space


![[0 _MHahkou-coeq5Py.webp]]

## [[li thread]] commands
-   PID: Unique process identifier
-   LWP: Unique thread identifier inside a process
-   NLWP: Number of threads for a given process
```sh
ps -efL # NLWP iz the number of threads of the process
```

