### type casting
- primitive numeric [[r data type]] can be cast with the `as` keyword

```rust
let x: i32 = 42;
let y: f64 = x as f64;  // int → float
let z: u8  = x as u8;   // int → smaller int (may truncate)
```

- conversions are also possible with the [[r trait]] `From<T>` and `Into<T>`

```rust
let s = String::from("hello");      // From<&str>
let s2: String = "world".into();    // Into<String>
```

- for conversions with can fail the `try_from` function can be used that return a `Result` [[r enum]] that contains the value of successful and the error if failed

```rust
let big: i32 = 300;
let small = u8::try_from(big);
```

- immutable types can be turned mutable with the `as_mut

# anki

START
Basic
[[r type casting]] is [[rust]]
- 3 different ways and when to use it
- how to change mutability?

Back: 
### type casting
- primitive numeric [[r data type]] can be cast with the `as` keyword

```rust
let x: i32 = 42;
let y: f64 = x as f64;  // int → float
let z: u8  = x as u8;   // int → smaller int (may truncate)
```

- conversions are also possible with the [[r trait]] `From<T>` and `Into<T>`

```rust
let s = String::from("hello");      // From<&str>
let s2: String = "world".into();    // Into<String>
```

- for conversions with can fail the `try_from` function can be used that return a `Result` [[r enum]] that contains the value of successful and the error if failed

```rust
let big: i32 = 300;
let small = u8::try_from(big);
```

- immutable types can be turned mutable with the `as_mut


Tags: code rust
<!--ID: 1756392328303-->
END