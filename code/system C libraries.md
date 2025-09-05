## system C libraries
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

# ----------------



# anki

START
Basic
[[system C libraries]]
- concepts
- how does it relate to the [[rust]] standard library and [[li syscall]]?

Back: 
## system C libraries
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

Tags: code rust
<!--ID: 1757084719331-->
END