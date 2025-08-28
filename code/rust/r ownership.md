## ownership
- each allocated memory space in the [[li heap]] is owned by a [[li stack]] [[r variable]]
- when the stack [[r variable]] goes out of scope the memory space is freed
- there can only be one owner, but the heap memory space be borrowed by passing a reference using the `&` operator

```rust
let s = String::from("hello");

let len = calculate_length(&s); // pass a reference
println!("{}", s);              // still valid

fn calculate_length(s: &String) -> usize {
    s.len()
}
```

### example: borrowing and taking ownership
- when a [[r struct]] is passed to a [[r function]] there are 3 different ways
	1) pass it as immutable [[r pointer#reference|reference]] (read only access)
	2) pass a mutable [[r pointer#reference|reference]] (read and write access)
	3) give ownership: the [[r function]] takes ownership and the caller loses it → data is deleted when the function execution is over

```rust
impl Foo {
    fn borrow(&self) { /* immutable borrow */ }
    fn borrow_mut(&mut self) { /* mutable borrow */ }
    fn take(self) { /* takes ownership */ }
}
```

### example: adding strings
- the add [[r trait]] is defined like the following

```rust
impl Add<&str> for String {
    type Output = String;

    fn add(self, rhs: &str) -> String { ... }
}
```

- that means it consumes the first operand and combines it with the second operand
- if we want to have all 3 strings we need to clone s1 and borrow s2

```rust
let s1 = String::from("Hello");
let s2 = String::from("World");

let s3 = s1.clone() + &s2;
println!("{}", s1);
println!("{}", s2);
println!("{}", s3);
```
# anki

START
Basic
[[r ownership]] in [[rust]]
- concept
- example: borrowing vs giving ownership of the [[r struct]] to a [[r function]]

Back: 
## ownership
- each allocated memory space in the [[li heap]] is owned by a [[li stack]] [[r variable]]
- when the stack [[r variable]] goes out of scope the memory space is freed
- there can only be one owner, but the heap memory space be borrowed by passing a reference using the `&` operator

```rust
let s = String::from("hello");

let len = calculate_length(&s); // pass a reference
println!("{}", s);              // still valid

fn calculate_length(s: &String) -> usize {
    s.len()
}
```

### example: borrowing and taking ownership
- when a [[r struct]] is passed to a [[r function]] there are 3 different ways
	1) pass it as immutable [[r pointer#reference|reference]] (read only access)
	2) pass a mutable [[r pointer#reference|reference]] (read and write access)
	3) give ownership: the [[r function]] takes ownership and the caller loses it → data is deleted when the function execution is over

```rust
impl Foo {
    fn borrow(&self) { /* immutable borrow */ }
    fn borrow_mut(&mut self) { /* mutable borrow */ }
    fn take(self) { /* takes ownership */ }
}
```

Tags: code rust
<!--ID: 1756052658861-->
END




START
Basic
what is wrong with the following [[rust]] snippet and how to make it work

```rust
let s1 = String::from("Hello");
let s2 = String::from("World");

let s3 = s1 + s2;
println!("{}", s1);
println!("{}", s2);
println!("{}", s3);
```

Back: 

```rust
let s1 = String::from("Hello");
let s2 = String::from("World");

let s3 = s1 + s2;  // s2 needs to be a reference
println!("{}", s1); // s1 was consumed
println!("{}", s2);
println!("{}", s3);
```
### example: adding strings
- the add [[r trait]] is defined like the following

```rust
impl Add<&str> for String {
    type Output = String;

    fn add(self, rhs: &str) -> String { ... }
}
```

- that means it consumes the first operand and combines it with the second operand
- if we want to have all 3 strings we need to clone s1 and borrow s2

```rust
let s1 = String::from("Hello");
let s2 = String::from("World");

let s3 = s1.clone() + &s2;
println!("{}", s1);
println!("{}", s2);
println!("{}", s3);
```

## ownership
- each allocated memory space in the [[li heap]] is owned by a [[li stack]] [[r variable]]
- when the stack [[r variable]] goes out of scope the memory space is freed
- there can only be one owner, but the heap memory space be borrowed by passing a reference using the `&` operator

```rust
let s = String::from("hello");

let len = calculate_length(&s); // pass a reference
println!("{}", s);              // still valid

fn calculate_length(s: &String) -> usize {
    s.len()
}
```


Tags: code rust
<!--ID: 1756383003748-->
END
