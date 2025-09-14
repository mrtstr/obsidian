### box
- [[r smart pointer]] to one [[r struct]] or [[r enum]] on the [[li heap]]
- needed when the size of not know at [[r compile time]] or the size is very large
- single [[r ownership|owner]] (normal [[rust]] ownership rules)
- [[r smart pointer]] on the [[li stack]] and data on the [[li heap]] 


```rust
let b = Box::new(42);
```

```
Stack:                Heap:
+---+                 +----+
| b | ----ptr-------> | 42 |
+---+                 +----+
```

- When `b` is dropped → heap memory freed.