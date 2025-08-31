### loops
- keyword `break` breaks the loop and `continue` forwards to the next iteration 

```rust
let mut n = 0;
loop {
    if n == 3 { break; }
    println!("{n}");
    n += 1;
}
```

```rust
let mut n = 0;
while n < 3 {
    println!("{n}");
    n += 1;
}
```

```rust
for i in 0..3 {
    println!("{i}");
}
```


# anki

START
Basic
[[r loops]]: 3 different ways to define them
Back: 
### loops
- keyword `break` breaks the loop and `continue` forwards to the next iteration 

```rust
let mut n = 0;
loop {
    if n == 3 { break; }
    println!("{n}");
    n += 1;
}
```

```rust
let mut n = 0;
while n < 3 {
    println!("{n}");
    n += 1;
}
```

```rust
for i in 0..3 {
    println!("{i}");
}
```
Tags: code rust
<!--ID: 1756646909273-->
END