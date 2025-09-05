### result
- in [[rust]] the [[r enum]] [[r result]] is similar to [[r option]] used for [[r error handling]]
- used as return value for operations that can go wrong like reading a file (e.g. file not found) or processing or a dataframe

```rust
enum Result<T, E> {
    Ok(T),   // success, contains value of type T
    Err(E),  // failure, contains error info
}
```


