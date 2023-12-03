
## [[li process image|process image]]
### [[li process image|process image summary]]
- a [[li process]] has its own [[li virtual memory]] space
- the [[li virtual memory]] space consists of 4 parts
	- [[li stack]]: for local (in scope) variables 
	- [[li heap]]: for manuel dynamicly allocated and deleted data
	- [[li data segment]]: for static/global variables that are 
	- [[li code segment]]: for the binary code that is executed ([[li program counter]] of each [[li thread]] keeping track of the location)

### [[li process image|process image components]]
![[li virtual memory#li virtual memory]]

![[li stack#li stack]]

![[li heap#li heap]]

![[li data segment#li data segment data segment]]


![[li code segment#li code segment code segment]]

![[Program_memory_layout.pdf.jpg]]


# Anki

START
Basic
## [[li process image]]
- relationship between the memory of a process and the [[li physical memory (RAM)]]
- segments of the memory of a [[li process]] (4 + 1)
Back: 
### [[li process image|process image summary]]
- a [[li process]] has its own [[li virtual memory]] space
- the [[li virtual memory]] space consists of 4 parts
	- [[li stack]]: for local (in scope) variables 
	- [[li heap]]: for manuel dynamicly allocated and deleted data
	- [[li data segment]]: for static/global variables that are 
	- [[li code segment]]: for the binary code that is executed ([[li program counter]] of each [[li thread]] keeping track of the location)


## [[li virtual memory]]
- abstraction layer between the [[li process]] and the [[li physical memory (RAM)]] and [[li disc]]
- from the [[li process]] perspective it is like having its own very lage private contious [[li memory]] space 
- in the [[li memory management unit]] of the [[li kernel]] a mapping of [[li physical memory (RAM)]] and [[li disc]] [[li memory paging|pages]] to [[li virtual memory]] [[li memory paging|pages]] is done (see [[li memory paging]])

## [[li stack]]
- segment inside the [[li virtual memory]] space of a [[li process]]
- execution memory of a [[li thread]] → a [[li process]] can have multiple [[li stack|stacks]]
- Fixed size (set when the [[li thread]] is created)
- contains 
	- local variables
	- function arguments
	- control information (e.g. adress pointers)
	- including return addresses'
- lifetime of data is limited to the end of the scope

#### [[li stack]] management
- manages by the [[li memory management unit]] of the [[li kernel]]
- LIFO (Last-In-First-Out) data structure
- when a function is called the stack grows and when the function is exited everything is removed except the reurn values (stack pointer set back to the possion of the function start)

### stack pointer 
is a small register that stores the memory address of the last data element added to the  [[li stack]]

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
<!--ID: 1701586495626-->
END


START
Basic
what is the difference between the [[li stack]], the [[li data segment]] and the [[li heap]]
Back: 
### [[li process image|process image summary]]
- a [[li process]] has its own [[li virtual memory]] space
- the [[li virtual memory]] space consists of 4 parts
	- [[li stack]]: for local (in scope) variables 
	- [[li heap]]: for manuel dynamicly allocated and deleted data
	- [[li data segment]]: for static/global variables that are 
	- [[li code segment]]: for the binary code that is executed ([[li program counter]] of each [[li thread]] keeping track of the location)

## [[li stack]]
- segment inside the [[li virtual memory]] space of a [[li process]]
- execution memory of a [[li thread]] → a [[li process]] can have multiple [[li stack|stacks]]
- Fixed size (set when the [[li thread]] is created)
- contains 
	- local variables
	- function arguments
	- control information (e.g. adress pointers)
	- including return addresses'
- lifetime of data is limited to the end of the scope

#### [[li stack]] management
- manages by the [[li memory management unit]] of the [[li kernel]]
- LIFO (Last-In-First-Out) data structure
- when a function is called the stack grows and when the function is exited everything is removed except the reurn values (stack pointer set back to the possion of the function start)

### stack pointer 
is a small register that stores the memory address of the last data element added to the  [[li stack]]

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



Tags: code linux
<!--ID: 1701619491872-->
END