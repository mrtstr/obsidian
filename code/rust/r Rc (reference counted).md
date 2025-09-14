#### reference counted
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