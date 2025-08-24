## function

### handling of input parameters
- parameters are only passed by position to [[r function]]
- parameters are passed by values per default → the [[r function]] takes [[r ownership]] and the data is cleared after the function scope is closed

```rust
fn takes_string(s: String) {   // takes ownership
    println!("Got: {}", s);
}

fn main() {
    let s = String::from("hello");
    takes_string(s);
    // println!("{}", s); ❌ ERROR: s was moved
}
```

- some [[r data type]] like int have are copied when passed

```rust
fn print_int(i: i32) { // takes ownership
	println!("{}", i);
}

fn main() {
	let number = 42;
	print_int(number);
	println!("{}", number); // works because number was copied
}
```

- often parameters are passed by [[r pointer#reference]] (mutable or immutable)

### return values
- the last expression is always returned (no `;`)

```rust
// works:
fn make_string() -> String {
    String::from("hello")  // last expression = return
}
// works:
fn make_string() -> String {
    let s = String::from("hello");
    s  // last expression = return
}
// doesnt work:
fn make_string() -> String {
    let s = String::from("hello");
}
fn main() {
    let s = make_string(); // ownership of returned String
    println!("{}", s);
}
```

### passing of functions
- in [[rust]] [[r function]] are first class citizens and can be passed to other [[r function]]

```rust
fn apply_twice(f: fn(i32) -> i32, x: i32) -> i32 {
    f(f(x))
}

fn add_one(x: i32) -> i32 {
    x + 1
}

fn main() {
    let result = apply_twice(add_one, 5);
    println!("{}", result); // 7
}
```



# anki

START
Basic
in [[rust]]
- how are parameters passed to [[r function]]?
- how do return values work?

Back: 
### handling of input parameters
- parameters are only passed by position to [[r function]]
- parameters are passed by values per default → the [[r function]] takes [[r ownership]] and the data is cleared after the function scope is closed

```rust
fn takes_string(s: String) {   // takes ownership
    println!("Got: {}", s);
}

fn main() {
    let s = String::from("hello");
    takes_string(s);
    // println!("{}", s); ❌ ERROR: s was moved
}
```

- some [[r data type]] like int have are copied when passed

```rust
fn print_int(i: i32) { // takes ownership
	println!("{}", i);
}

fn main() {
	let number = 42;
	print_int(number);
	println!("{}", number); // works because number was copied
}
```

- often parameters are passed by [[r pointer#reference]] (mutable or immutable)

### return values
- the last expression is always returned (no `;`)

```rust
// works:
fn make_string() -> String {
    String::from("hello")  // last expression = return
}
// works:
fn make_string() -> String {
    let s = String::from("hello");
    s  // last expression = return
}
// doesnt work:
fn make_string() -> String {
    let s = String::from("hello");
}
fn main() {
    let s = make_string(); // ownership of returned String
    println!("{}", s);
}
```
Tags: code rust
<!--ID: 1756052658845-->
END


START
Basic
- what is happening in the following [[rust]] code snippets?

```rust
fn takes_string(s: String) {
    println!("Got: {}", s);
}

fn main() {
    let s = String::from("hello");
    takes_string(s);
    println!("{}", s);
}
```

```rust
fn print_int(i: i32) {
	println!("{}", i);
}

fn main() {
	let number = 42;
	print_int(number);
	println!("{}", number); 
}
```

Back: 
### handling of input parameters
- parameters are only passed by position to [[r function]]
- parameters are passed by values per default → the [[r function]] takes [[r ownership]] and the data is cleared after the function scope is closed

```rust
fn takes_string(s: String) {   // takes ownership
    println!("Got: {}", s);
}

fn main() {
    let s = String::from("hello");
    takes_string(s);
    // println!("{}", s); ❌ ERROR: s was moved
}
```

- some [[r data type]] like int have are copied when passed

```rust
fn print_int(i: i32) { // takes ownership
	println!("{}", i);
}

fn main() {
	let number = 42;
	print_int(number);
	println!("{}", number); // works because number was copied
}
```

- often parameters are passed by [[r pointer#reference]] (mutable or immutable)


Tags: code rust
<!--ID: 1756052658848-->
END