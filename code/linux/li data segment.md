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

# anki

START
Basic
data segment
- 2 different types
- lifetime
- difference to[[li stack]]
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

![[Program_memory_layout.pdf 3.jpg]]
Tags: code linux
<!--ID: 1701528585794-->
END