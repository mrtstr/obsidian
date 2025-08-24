### deref
- [[r trait]] that implements the behavior for referencing of [[r struct]] for example when dereferencing a [[r pointer]]
- this [[r function]] is called when the `deref` operator `*` is called

```rust
fn main() {
    let b = Box::new(42);
    println!("{}", *b); // deref via explicit operator
    // 42
    println!("{}", b);  
    // deref is called via Display implementation of Box
    // not always eqivalnt like here
    // 42
}
```


# anki

START
Basic
what is the [[r deref]] function in [[rust]]?

Back: 
### deref
- [[r trait]] that implements the behavior for referencing of [[r struct]] for example when dereferencing a [[r pointer]]
- this [[r function]] is called when the `deref` operator `*` is called

```rust
fn main() {
    let b = Box::new(42);
    println!("{}", *b); // deref via explicit operator
    // 42
    println!("{}", b);  
    // deref is called via Display implementation of Box
    // not always eqivalnt like here
    // 42
}
```
Tags: code rust
<!--ID: 1756052658831-->
END
