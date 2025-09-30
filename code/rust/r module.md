### module
- in [[rust]] a [[r module]] is like a namespace for code organization inside a [[r crate]]
- it groups related items ([[r function]], [[r struct]], [[r trait]],  submodules, …)

inline [[r module]]:

```rust
mod math {
    pub fn add(a: i32, b: i32) -> i32 { a + b }
}
```

file based [[r module]] (code organized in separate files):

```rust
// lib.rs
mod math; // Rust will look for `math.rs` or `math/mod.rs`
```

```rust
// math.rs
pub fn add(a: i32, b: i32) -> i32 { a + b }
```

usage:

```rust
let x = math::add(2, 3);
```