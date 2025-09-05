### macro
- in [[rust]] a [[r macro]] is a compile time meta programming feature → code that writes code
- expanded during the [[compiler|compilation process]]

```rust
macro_rules! print_type {
    ($val:expr) => {
        println!("{}: {}", stringify!($val), std::any::type_name::<_>());
    };
}
```

![[compiler#compiler]]