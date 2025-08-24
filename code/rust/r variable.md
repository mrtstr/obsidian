### variable
#### stack variables
- local variables live in the [[li stack]]

```rust
let x = 5;     // default is mut
let mut x = 6;
let (x, y) = (1, 2); // declaring multiple variables
```

- types are inferred but can be declared explicit
- when no value is assigned initially the type has to be declared

```rust
let mut x: i32 = 5;
let mut z: i32;
```

- the following creates a new variable instead of overwriting the old one

```rust
let a = 5;
let a = a + 1;
```

#### data sentiment variables
- [[li data segment]] variables are declared with `static` or `const`
- `const` is immutable and set at compile time and set inside functions and is only accessible in that scope
- `static` can be mutable (but this is unsafe) and is usually descaled at module level and can be imported

```rust
static GLOBAL: i32 = 42;    // data segment
const PI: f64 = 3.14;       // usually .rodata
```

#### heap variables
- when variables are declared with [[r pointer#smart pointer]] they live on the [[li heap]] and are managed by the [[r ownership]] mechanism

```rust
fn main() {
    let s = String::from("hello"); // heap-allocated string buffer
    let v = vec![1, 2, 3];         // vector data on heap
}
```

#### string example
- `hello` is stored in the [[li data segment]] (read only) at compile time
- `String::from` allocates space on the [[li heap]] and copies the string into that [[li memory]] at runtime
- `s` is a [[r pointer#smart pointer]] to that memory address that takes [[r ownership]]

```rust
let mut s = String::from("hello");
```

# anki

START
Basic
how are [[r variable]] on the [[li heap]], [[li stack]], and [[li data segment]] managed/declared in [[rust]]?

Back: 
#### stack variables
- local variables live in the [[li stack]]

```rust
let x = 5;     // default is mut
let mut x = 6;
let (x, y) = (1, 2); // declaring multiple variables
```

- types are inferred but can be declared explicit
- when no value is assigned initially the type has to be declared

```rust
let mut x: i32 = 5;
let mut z: i32;
```

- the following creates a new variable instead of overwriting the old one

```rust
let a = 5;
let a = a + 1;
```

#### data sentiment variables
- [[li data segment]] variables are declared with `static` or `const`
- `const` is immutable and set at compile time and set inside functions and is only accessible in that scope
- `static` can be mutable (but this is unsafe) and is usually descaled at module level and can be imported

```rust
static GLOBAL: i32 = 42;    // data segment
const PI: f64 = 3.14;       // usually .rodata
```

#### heap variables
- when variables are declared with [[r pointer#smart pointer]] they live on the [[li heap]] and are managed by the [[r ownership]] mechanism

```rust
fn main() {
    let s = String::from("hello"); // heap-allocated string buffer
    let v = vec![1, 2, 3];         // vector data on heap
}
```


Tags: code rust
<!--ID: 1756052658855-->
END


START
Basic
- what is happening in this [[rust]] snippet at compile time and exec time related to the segments of the [[li memory]]

```rust
let mut s = String::from("hello");
```

Back: 
#### string example
- `hello` is stored in the [[li data segment]] (read only) at compile time
- `String::from` allocates space on the [[li heap]] and copies the string into that [[li memory]] at runtime
- `s` is a [[r pointer#smart pointer]] to that memory address that takes [[r ownership]]

```rust
let mut s = String::from("hello");
```

Tags: code rust
<!--ID: 1756052658858-->
END