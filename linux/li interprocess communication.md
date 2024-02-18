af-   **Independent Processes** operating concurrently on a systems are those that can neither affect other processes or be affected by other processes.
-   **Cooperating Processes** are those that can affect or be affected by other processes. There are several reasons why cooperating processes are allowed:
    -   Information Sharing - There may be several processes which need access to the same file for example. ( e.g. pipelines. )
    -   Computation speedup - Often a solution to a problem can be solved faster if the problem can be broken down into sub-tasks to be solved simultaneously ( particularly when multiple processors are involved. )
    -   Modularity - The most efficient architecture may be to break a system down into cooperating modules. ( E.g. databases with a client-server architecture. )
    -   Convenience - Even a single user may be multi-tasking, such as editing, compiling, printing, and running the same code in different windows.

Cooperating processes require some type of inter-process communication, which is most commonly one of two types: Shared Memory systems or Message Passing systems. Figure 3.13 illustrates the difference between the two systems:


-   Shared Memory is faster once it is set up, because no system calls are required and access occurs at normal memory speeds. However it is more complicated to set up, and doesn't work as well across multiple computers. Shared memory is generally preferable when large amounts of information must be shared quickly on the same computer.
-   Message Passing requires system calls for every message transfer, and is therefore slower, but it is simpler to set up and works well across multiple computers. Message passing is generally preferable when the amount and/or frequency of data transfers is small, or when multiple computers are involved.

![[li memory sharing]]

[[li process messaging]]

![[li signal]]

![[linux/li pipe#li pipe]]

![[li redirection]]

![[li standard streams]]


![[li shared memory]]