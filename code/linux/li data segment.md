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

## relevant

![[li process image#li process image process image summary]]
# anki

START
Basic
data segment
- 2 different types
- lifetime
- difference to [[li stack]]
Back: 
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


### [[li process image|process image summary]]
- a [[li process]] has its own [[li virtual memory]] space
- the [[li virtual memory]] space consists of 4 parts
	- [[li stack]]: for local (in scope) variables 
	- [[li heap]]: for manuel dynamicly allocated and deleted data
	- [[li data segment]]: for static/global variables that are 
	- [[li code segment]]: for the binary code that is executed ([[li program counter]] of each [[li thread]] keeping track of the location)

![[Program_memory_layout.pdf 3.jpg]]
Tags: code linux
<!--ID: 1701528585794-->
END