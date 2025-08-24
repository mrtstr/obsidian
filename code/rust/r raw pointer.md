### raw pointer
- similar concept to C/C++ pointers
- now ownership enforced just the raw [[li memory]] address in the memory
- [[r data type]] `*mut T` or `*const T`
- can be referenced using the `*` operator but only in an [[r unsafe]] scope
- the address from a [[r variable]] can be extracted using the `&` operator

```rust
let x = 42;
let r: *const i32 = &x as *const i32;
unsafe {
    println!("{}", *r); // dereferencing requires unsafe
}
```