### What happens at runtime?
1. **Load the program into memory**
    - OS loads your binary into RAM.
    - OS also loads required **dynamic libraries** (`libc.so`, `libm.so`, `libpthread.so`, etc.) into the process memory.
2. **Dynamic symbol resolution**
    - Loader connects your program’s unresolved calls (e.g. `malloc`) to the correct addresses inside libc.
    - Think of it like “plugging in the missing wires.”
3. **Run startup code**
    - Before `main()` in C (or `fn main()` in Rust) runs, startup code from libc (or Rust runtime) sets things up:
        - Initialize heap allocator.
        - Initialize thread-local storage.
        - Register destructors for `atexit()`.
4. **Program executes**
    - Now your code + Rust std/core/alloc runs normally.
    - When you call `Vec::new()`, Rust may call libc’s `malloc` → which eventually makes syscalls (`mmap`, `brk`).
5. **Syscalls → Kernel**
    - If you call `println!`, it eventually goes:
```
println! → std::io → libc::write → syscall(write) → kernel → hardware
```

**Exit**

- When `main` returns, libc cleans up (flush buffers, free resources), then makes the `exit` syscall.