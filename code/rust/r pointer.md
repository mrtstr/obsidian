## pointer
- pointers are variables that hold [[li memory]] addresses
- in rust there are 3 types of pointers
	1)  [[r reference]] (`&T`, `&mut T`): save borrowing pointers that do not own
	2) [[r raw pointer]] (`*mut T`, `*const T`): unsafe with no ownership rules enforced
	3) [[r smart pointer]] (`Box`, `Vec`, ...): [[r struct]] that contain a raw pointer plus extra metadata and  implement additional logic for memory management like `Deref`/`Drop`, own their data


# --------------

![[r reference#reference]]

![[r raw pointer#raw pointer]]

![[r smart pointer#smart pointer]]





# anki

START
Basic
3 [[r pointer]] concepts in [[rust]]
Back: 
## pointer
- pointers are variables that hold [[li memory]] addresses
- in rust there are 3 types of pointers
	1)  [[r reference]] (`&T`, `&mut T`): save borrowing pointers that do not own
	2) [[r raw pointer]] (`*mut T`, `*const T`): unsafe with no ownership rules enforced
	3) [[r smart pointer]] (`Box`, `Vec`, ...): [[r struct]] that contain a raw pointer plus extra metadata and  implement additional logic for memory management like `Deref`/`Drop`, own their data

### reference
- in [[rust]] a [[r reference]] is a [[r pointer]] that borrows the data (it doesn't take [[r ownership]])
- the `&` operator reads the memory address (= [[r reference]]) from and [[r variable]]
- a [[r reference]] is often passed to a [[r function]]
- the following rule applies: there can be either one mutable reference or multiple immutable references per scope

- the following two work because there is only one reference in a scope at a time, but the second won't compile

```rust
let mut s = String::from("hello");

{
	let r: &String = &s; // immutable borrow
	println!("{}", r); // used here
}

{
	// now r is no longer used, so we can borrow mutably
	let mr: &mut String = &mut s;
	println!("{}", mr);
}
{
	// this does not work
	let mr: &mut String = &mut s;
	let r: &String = &s; // immutable borrow
}
```

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

Tags: code rust
<!--ID: 1756052658853-->
END