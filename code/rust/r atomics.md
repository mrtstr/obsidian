### atomics
- more lightweight and low level than [[r RwLock (read–write lock)]] and [[r Mutex (mutual exclusion)]]
- only for simple data structures like bools or int and ensures [[r atomic operation]] when incrementing for example
- used for implementing [[r Arc (atomic reference counted)]]
- for more complex cases use  [[r RwLock (read–write lock)]] and [[r Mutex (mutual exclusion)]]


![[r atomic operation#atomic operation]]