### atomic reference counted
- [[r Rc (reference counted)]] [[r smart pointer]] with [[r atomic operation]] → [[r thread]] safe

![[r Rc (reference counted)#reference counted]]

# ----------

![[r atomic operation#atomic operation]]

# --------------

![[r smart pointer#smart pointer]]

# anki

START
Basic
[[r smart pointer]] in [[rust]]
- box vs reference counted vs atomic reference counted
Back: 

### types of smart pointers
- **`Box<T>`** → one owner, heap storage.
- **`Rc<T>`** → many owners, single-thread, refcount.
- **`Arc<T>`** → many owners, multi-thread, atomic refcount.
- **`RefCell<T>`** → one owner, runtime borrow rules (panics if violated).
- **`Mutex<T>`** → one writer at a time across threads.
- **`RwLock<T>`** → many readers or one writer across threads.

| Smart Pointer | Ownership         | Thread-safe? | Mutability check | Common use case                       |
| ------------- | ----------------- | ------------ | ---------------- | ------------------------------------- |
| `Box<T>`      | Single owner      | N/A          | Compile-time     | Heap storage, recursion               |
| `Rc<T>`       | Shared (refcount) | ❌            | Compile-time     | Shared immutable data (single-thread) |
| `Arc<T>`      | Shared (refcount) | ✅            | Compile-time     | Shared immutable data (multi-thread)  |
| `RefCell<T>`  | Single owner      | ❌            | Runtime          | Interior mutability (single-thread)   |
| `Mutex<T>`    | Shared (lock)     | ✅            | Runtime (lock)   | Shared mutable data (multi-thread)    |
| `RwLock<T>`   | Shared (lock)     | ✅            | Runtime (lock)   | Many readers or one writer            |

#### (atomic) reference counted
- [[r smart pointer]] with non standard [[r ownership]] rules
- [[r smart pointer]] on the [[li stack]] and data on the [[li heap]] 
- Multiple [[r ownership|owners]], single-[[li thread]] or multiple-[[li thread]] of [[r atomic operation]]

```rust
use std::rc::Rc;
let a = Rc::new(42);
let b = Rc::clone(&a);

use std::sync::Arc;
let a = Arc::new(42);
let b = Arc::clone(&a);

```

```
Stack:                   Heap:
+---+      +---+         +--------------+
| a |----->|   |         | Rc box:      |
+---+      +---+         | refcount=2   |
                         | value = 42   |
+---+                    +--------------+
| b |--------------------^
+---+

```

- Both `a` and `b` point to the same heap box.
- Refcount = 2. When last `Rc` is dropped, memory is freed.

____________

### atomic operation
An [[r atomic operation]] is one that is **indivisible**:
- It either happens completely, or not at all.
- No other thread can “see” it halfway done.

- makes operations [[li thread]] safe but add overhead

example
- without [[r atomic operation]]

```rust
let mut counter = 0; // shared
// Thread A: read counter (0), add 1 → write 1
// Thread B: read counter (0), add 1 → write 1
// Final value = 1 (wrong, lost update)
```

- with [[r atomic operation]]

```rust
use std::sync::atomic::{AtomicUsize, Ordering};

let counter = AtomicUsize::new(0);

// In each thread:
counter.fetch_add(1, Ordering::SeqCst);
```
### smart pointer
- [[r struct]] that contains the [[r pointer#raw pointer]] plus metadata like the length and additional behavior for memory management like [[r drop]]
- takes [[r ownership]] of its data
- can have additional logic for releasing the data ([[r drop]]) or borrowing [[r deref]]

- example how the [[r struct]] looks like for a `Vec` [[r smart pointer]] (with `T` the [[r generic type]])

```rust
pub struct Vec<T> {
    ptr: *mut T,   // raw pointer to heap buffer
    len: usize,    // number of elements actually in use
    cap: usize,    // number of elements allocated
}
impl<T> Drop for Vec<T> {
    fn drop(&mut self) {
        // 1. Drop all elements (run their destructors)
        // 2. Free the heap buffer
    }
}
```


- example: allocation of a string: the fields of the [[r struct]] for `ptr` and so on are [[r encapsulation|private]] but can be accessed with a getter method

```rust
let mut s = String::from("hello");
s.as_ptr()   // raw pointer to the memory adress (raw pointer)
s.len()   // number saved bytes
s.capacity() // number of allocated bytes
```


Tags: code rust
<!--ID: 1756656420129-->
END