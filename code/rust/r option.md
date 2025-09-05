### option
- [[r enum]] for handling values that can be none (see [[r null handling]])
- null values are handled with the [[r enum]] [[r option]] than can be `Some` or `None`

```rust
enum Option<T> { Some(T), None }
```

