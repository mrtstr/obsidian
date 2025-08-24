### smart pointer
- [[r struct]] that contains the [[r pointer#raw pointer]] plus metadata like the length and additional behavior for memory management like [[r drop]]
- takes [[r ownership]] of its data
- can have additional logic for releasing the data ([[r drop]]) or borrowing [[r deref]]

- example how the [[r struct]] looks like for a `Vec` [[r smart pointer]] (with `T` the [[r generic type]])

```rust
pub struct Vec<T> {
    ptr: *mut T,   // raw pointer to heap buffer
    len: usize,    // number of elements actually in use
    cap: usize,    // number of elements allocated
}
impl<T> Drop for Vec<T> {
    fn drop(&mut self) {
        // 1. Drop all elements (run their destructors)
        // 2. Free the heap buffer
    }
}
```


- example: allocation of a string: the fields of the [[r struct]] for `ptr` and so on are [[r encapsulation|private]] but can be accessed with a getter method

```rust
let mut s = String::from("hello");
s.as_ptr()   // raw pointer to the memory adress (raw pointer)
s.len()   // number saved bytes
s.capacity() // number of allocated bytes
```


# anki

START
Basic
[[r smart pointer]] in [[rust]]
- concept
- code example
Back: 
### smart pointer
- [[r struct]] that contains the [[r pointer#raw pointer]] plus metadata like the length and additional behavior for memory management like [[r drop]]
- takes [[r ownership]] of its data
- can have additional logic for releasing the data ([[r drop]]) or borrowing [[r deref]]

- example how the [[r struct]] looks like for a `Vec` [[r smart pointer]] (with `T` the [[r generic type]])

```rust
pub struct Vec<T> {
    ptr: *mut T,   // raw pointer to heap buffer
    len: usize,    // number of elements actually in use
    cap: usize,    // number of elements allocated
}
impl<T> Drop for Vec<T> {
    fn drop(&mut self) {
        // 1. Drop all elements (run their destructors)
        // 2. Free the heap buffer
    }
}
```


- example: allocation of a string: the fields of the [[r struct]] for `ptr` and so on are [[r encapsulation|private]] but can be accessed with a getter method

```rust
let mut s = String::from("hello");
s.as_ptr()   // raw pointer to the memory adress (raw pointer)
s.len()   // number saved bytes
s.capacity() // number of allocated bytes
```

Tags: code rust
<!--ID: 1756052658828-->
END