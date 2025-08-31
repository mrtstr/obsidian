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


# anki

START
Basic
[[r atomic operation]] in [[rust]]
- concept
- advantages and costs
- examples why its needed
Back: 
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
Tags: code rust
<!--ID: 1756656420121-->
END