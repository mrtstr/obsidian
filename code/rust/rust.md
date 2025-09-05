

- **`std` (the standard library)**
    - Contains most of the everyday stuff: collections, I/O, threads, filesystem, etc.
    - When you `use std::fs`, you’re using Rust library functions implemented in Rust (sometimes with `unsafe` parts that call into system APIs).
- **`core`**
    - A smaller library with _no OS dependencies_.
    - Provides basic types (`Option`, `Result`, `slice`, arithmetic) that even `std` builds upon.
    - This is what you get in `#![no_std]` environments (like embedded).
- **`alloc`**
    - Sits between `core` and `std`.
    - Adds heap-based things like `Vec`, `Box`, `String`, but doesn’t itself do I/O.

- **System / libc layer (below Rust libraries)**
    - When you call something like `std::fs::File::open()`, under the hood it eventually calls **system calls** (`open` on Linux, `CreateFileW` on Windows).
        
    - Rust doesn’t reinvent those — it wraps them in safe abstractions.

```
Rust source code
   ↓
Compiler (rustc)
   ↓
Standard Library (std) ← (Rust-specific library functions)
   ↓
Core / Alloc (subset usable without OS)
   ↓
System C libraries / syscalls (shared across languages)
   ↓
Operating System Kernel
   ↓
Hardware
```