[[li kernel process]]

### keys responisbilities 
1.  [[li memory management unit]] Keep track of how much memory is used to store what, and where
2.  [[li process management]] Determine which processes can use the central processing unit (CPU), when, and for how long
3.  **Device drivers:** Act as mediator/interpreter between the hardware and [[li process|processes]]
4.  [[li syscall]] processing [[li syscall]] from [[li user process]]

![[1_10_UserToKernelMode.jpg]]

 An OS is responsible for the following tasks with regards to process management:
### 1.6 Process Management
-   Creating and deleting both user and system processes
 -   Ensuring that each process receives its necessary resources, without interfering with other processes.
-   Suspending and resuming processes
-   Process synchronization and communication
-   Deadlock handling

### 1.7 Memory Management
An OS is responsible for the following tasks with regards to memory management: 
-   Keeping track of which blocks of memory are currently in use, and by which processes. -   Determining which blocks of code and data to move into and out of memory, and when.
-   Allocating and deallocating memory as needed. ( E.g. new, malloc )