### alloc
- [[r crate]] that are even lower than [[r std]] and always included in the binary during the [[compiler#code generation]]
- second layer of the [[rust]] [[r std]]
- build up on [[r core]] but assumes a **heap allocator exists** (part of the [[system C libraries]])
- contains the language features that deal with [[li heap]] allocation
- Examples: [[r box]], [[r vec]], [[r struct]], [[r hash map]]

```
Your Rust code (Vec, Box, String)
   ↓
alloc crate (needs heap allocation)
   ↓
std::alloc::System (default allocator)
   ↓
libc malloc/free (system C library)
   ↓
OS syscalls (mmap/brk on Linux, HeapAlloc on Windows)
   ↓
Kernel memory manager
```


# anki

START
Basic
memory in the [[li heap]] is allocated in a [[rust]] program
- 3 layers that are involved between the program and the [[li kernel]] that are involved

Back: 

### alloc
- [[r crate]] that are even lower than [[r std]] and always included in the binary during the [[compiler#code generation]]
- second layer of the [[rust]] [[r std]]
- build up on [[r core]] but assumes a **heap allocator exists** (part of the [[system C libraries]])
- contains the language features that deal with [[li heap]] allocation
- Examples: [[r box]], [[r vec]], [[r struct]], [[r hash map]]

```
Your Rust code (Vec, Box, String)
   ↓
alloc crate (needs heap allocation)
   ↓
std::alloc::System (default allocator)
   ↓
libc malloc/free (system C library)
   ↓
OS syscalls (mmap/brk on Linux, HeapAlloc on Windows)
   ↓
Kernel memory manager
```

### system C libraries
- the [[system C libraries]] called **libc** is provided by the operating system
- abstraction layer on top of the [[li syscall]]
- used across all programming languages
- for example `printf`, `malloc`, `fopen` wraps the [[li syscall]] [[li open]] [[li write]] and [[li read]]
- in [[rust]] the [[system C libraries]] are mapped during the [[compiler#linking]] and resolved at runtime

```
Rust code (println!)
   ↓
Rust std (formatting, buffering)
   ↓
libc (write, malloc, etc.)
   ↓
syscall (kernel interface)
   ↓
Operating System Kernel
   ↓
Hardware
```

### std
- last layer of the standard library in [[rust]]
- depends on [[r core]], [[r alloc]] and the [[system C libraries]] from the OS

Examples:
- Filesystem: `std::fs::File`
- Networking: `std::net::TcpStream`
- Threads: `std::thread`
- Channels: `std::sync::mpsc`
- Time, random numbers, environment variables, process management.


### core
- [[r crate]] that are even lower than [[r std]] and always included in the binary (together with [[r alloc]]) during the [[compiler#code generation]]
- first layer of the [[rust]] standard library ([[r std]])
- contains bare essentials with no dependency on the [[li heap]] and the [[system C libraries]] of the OS
- Even in `#![no_std]` environments, you’ll still pull in `core`

Examples:
- Basic [[r data type]]: [[r option]], [[r result]], `str`, [[r slicing]], [[r array]], [[r tuple]]...
- [[r trait]]: `Copy`, `Clone`, `Iterator`, [[r drop]], arithmetic traits...
- Utilities: [[r panic]]

Tags: code rust
<!--ID: 1757084719335-->
END