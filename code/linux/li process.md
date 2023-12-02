## [[li process]] concept
- container of isolation which can hold system resources 
- multiple [[li thread|threads]] can run inside a [[li process]]

## basic [[li process]] properties
- **PID**: Unique Process ID given to each process.
- **User**: Username of the process owner.
- **S**: state of the process
- **Command**: [[li shell command]] used to activate the process.
- [[li standard streams]]: 
	- [[li stdin]] (e.g. keyboard, [[li pipeline|piped]] from another [[li process]] ...)
	- [[li stdout]] ([[li terminal]], [[li pipeline|piped]] to another [[li process]], a [[li file]] ...)
	- [[li stderr]] ([[li terminal]], [[li pipeline|piped]] to another [[li process]], a [[li file]] ...)
- return a [[li return code]] back to their [[li parent process]] on termination
- have a [[li working directory]]

environment variables: key-values which get inherited across processes.


## types [[li user process]] and [[li kernel process]]


## [[li process]] states
-   `D` = **uninterruptible sleep**: waiting for a resource to be available (will wakeup to handle signals)
-   `R` = **running**: running or it’s ready to run
-   `S` = **sleeping**: waiting for a resource to be available (will not wakeup to handle signals)
-   `T` = **traced or stopped**
-   `Z` = **zombie**: terminated child process that remains in the system's process table while waiting for its parent process to collect its exit status

![[ProcessState.png]]


## memory layout
- a [[li process]] has its own [[li virtual memory]] space
- the [[li virtual memory]] space consists of 4 parts
	1) [[li stack]]
	2) [[li heap]]
	3) [[li data segment]]
	4) [[li code segment]]
- on 

![[li virtual memory#li virtual memory]]

![[li stack#li stack]]

![[li heap#li heap]]

![[li data segment#li data segment data segment]]


![[li code segment#li code segment instruction segment]]

![[Program_memory_layout.pdf.jpg]]

## process execution

![[li thread#li thread]]

## commands

![[li ps#`ps`]]

![[li top and htop#top]]

![[li kill#kill]]

![[li renice#`renice`]]


# Anki

ART
Basic
## memory layout of a [[li process]]
- relationship between the memory of a process and the [[li physical memory (RAM)]]
- segments of the memory of a [[li process]] (4 + 1)
Back: 

- a [[li process]] has its own [[li virtual memory]] space
- the [[li virtual memory]] space consists of 4 parts
	1) [[li stack]]
	2) [[li heap]]
	3) [[li data segment]]
	4) [[li code segment]]


## [[li virtual memory]]
- abstraction layer between the [[li process]] and the [[li physical memory (RAM)]] and [[li disc]]
- from the [[li process]] perspective it is like having its own very lage private contious [[li memory]] space 
- in the [[li memory management unit]] of the [[li kernel]] a mapping of [[li physical memory (RAM)]] and [[li disc]] [[li memory paging|pages]] to [[li virtual memory]] [[li memory paging|pages]] is done (see [[li memory paging]])

## [[li stack]]
- segment inside the [[li virtual memory]] space of a [[li process]]
- execution memory of a [[li thread]] → a [[li process]] can have multiple [[li stack|stacks]]
- **Fixed size:**(set when the [[li thread]] is created)
- contains local variables, function arguments, and control information (e.g. adress pointers), including return addresses
- manages by the [[li memory management unit]] of the [[li kernel]]
- LIFO (Last-In-First-Out) data structure
- lifetime of data is limited to the end of the scope
- when a function is called the stack grows and when the function is exited everything is removed except the reurn values

## [[li heap]]
- segment inside the [[li virtual memory]] space of a [[li process]]
- [[li memory]] for dynamic memory storage for large data structures and objects with dynamic lifetimes'
- memory can be allocated or deallocated manuelly during the program execution during the processes liefetime

## [[li data segment|data segment]]
- segment inside the [[li virtual memory]] space of a [[li process]]
- contains gloabal / static variables
- remains in memory throughout the life of the [[li process]] 
- read/write

### initializes data
The **data segment** contains initialized static variables

```C
int i = 3;
char a[] = "Hello World";
static int b = 2023;    // Initialized static global variable
void foo (void) {
  static int c = 2023; // Initialized static local variable
}
```


### bss segment (uninitializes data)
- contains uninitialized static data, both variables and constants,
```C
static int i;
static char a[12];
```




## [[li code segment|instruction segment]]
- segment inside the [[li virtual memory]] space of a [[li process]]
- contains executable binary code (mapped from the [[li disc]] to the [[li virtual memory]] of the [[li process]])
- read only 

![[Program_memory_layout.pdf 1.jpg]]


Tags: code linux

END

START
Basic
[[linux]] process states
- 5 short name, full name explaination
- overview diagramm

Back: 

## [[li process]] states
-   `D` = **uninterruptible sleep**: waiting for a resource to be available (will wakeup to handle signals)
-   `R` = **running**: running or it’s ready to run
-   `S` = **sleeping**: waiting for a resource to be available (will not wakeup to handle signals)
-   `T` = **traced or stopped**
-   `Z` = **zombie**: terminated child process that remains in the system's process table while waiting for its parent process to collect its exit status

![[ProcessState 1.png]]

Tags: code linux
<!--ID: 1699690123163-->
END

START
Basic
basic [[li process]] properties (4)
Back: 

- **PID**: Unique Process ID given to each process.
- **User**: Username of the process owner.
- **S**: state of the process
- **Command**: Command used to activate the process.

Tags: code linux
<!--ID: 1699690123177-->
END


START
Basic
 [[li process]] 
 - commands to manage (2) and display (2) them
Back: 

## `ps`
print out process status of the **currently running** processes 
- `-A` or `-e` show all processes (like [[li top and htop]] but without realtime updates)
- `-T` show only processes connected to the used terminal (default)
- `-f` show more details

## `top`
- show table of runnnig [[li process]] currently being managed by the Linux kernel with properties like resources' usage
- real-time view of a running system

## `kill`
- kill a [[li process]] by sending a kill [[li signal]]
- there are different types of kill signals (most commong SIGKILL `-9`)
- usage `kill -9 [pid]`

## `renice`
Change the niceness values of a user (regular) [[li process]] or a group of user processes
`renice [value] -p [pids]` e.g.  `renice 5 -p 2 10` (change nicesness of process with pids 2 and 10 to 5)
`renice [value] -u [user]` e.g.  `renice -20 -u user1` (change the niceness of all processes of user1 to -20)

Tags: code linux
<!--ID: 1699690123180-->
END