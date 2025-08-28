## generic type
- [[r function]] that work with a [[r generic type]] can be implemented as follows
- at [[r compile time]] the [[r compiler]] creates multiple versions of the functions for all [[r data type]] of values it is used for 

```rust
fn identity<T>(x: T) -> T { x }

let a = identity(10);                // T = i32
let b = identity(String::from("x")); // T = String
```

#### constraints
- it's possible to define contains, like in this example the [[r data type]] has to implement the [[r trait]] `XYZ` or otherwise it won't compile

```rust
fn identity<T: XYZ>(x: T) -> T {
    x // valid only for types that implement XYZ
}
```

- the constraints can be made explicit like in the following equivalent example

```rust
fn identity<T>(x: T) -> T
where
    T: XYZ,
{
    x
}
```

### multiple generic types
- It's possible to have multiple [[r generic type]]
- this means `T: std::ops::Add<Output = T>` the input [[r data type]] has to implement the `Add` [[r trait]] and `T` is the [[r data type]] of the output of the add operation

```rust
fn pair<A, B>(a: A, b: B) -> (A, B) { (a, b) }
let i=1;
let j=10;
pair(j, i)
```



```rust
fn add_all<T: std::ops::Add<Output = T>, U: std::ops::Add<Output = U>>(x: T, y: T, u: U, v: U) -> (T, U) {
    (x + y, u + v)
}
```


# anki

START
Basic
functions that can take multiple data types in [[rust]]
- concept
- how is it used

Back: 
## generic type
- [[r function]] that work with a [[r generic type]] can be implemented as follows
- at [[r compile time]] the [[r compiler]] creates multiple versions of the functions for all [[r data type]] of values it is used for 

```rust
fn identity<T>(x: T) -> T { x }

let a = identity(10);                // T = i32
let b = identity(String::from("x")); // T = String
```

#### constraints
- it's possible to define contains, like in this example the [[r data type]] has to implement the [[r trait]] `XYZ` or otherwise it won't compile

```rust
fn identity<T: XYZ>(x: T) -> T {
    x // valid only for types that implement XYZ
}
```

- the constraints can be made explicit like in the following equivalent example

```rust
fn identity<T>(x: T) -> T
where
    T: XYZ,
{
    x
}
```

### multiple generic types
- It's possible to have multiple [[r generic type]]
- this means `T: std::ops::Add<Output = T>` the input [[r data type]] has to implement the `Add` [[r trait]] and `T` is the [[r data type]] of the output of the add operation

```rust
fn pair<A, B>(a: A, b: B) -> (A, B) { (a, b) }
let i=1;
let j=10;
pair(j, i)
```



```rust
fn add_all<T: std::ops::Add<Output = T>, U: std::ops::Add<Output = U>>(x: T, y: T, u: U, v: U) -> (T, U) {
    (x + y, u + v)
}
```
Tags: code rust
<!--ID: 1756383003751-->
END


START
Basic
[[rust]] example: write a [[r function]] that take two instances of arbitrary [[r data type]] and return a tuple (types might be different)
Back: 

### multiple generic types
- It's possible to have multiple [[r generic type]]
- this means `T: std::ops::Add<Output = T>` the input [[r data type]] has to implement the `Add` [[r trait]] and `T` is the [[r data type]] of the output of the add operation

```rust
fn pair<A, B>(a: A, b: B) -> (A, B) { (a, b) }
let i=1;
let j=10;
pair(j, i)
```
## generic type
- [[r function]] that work with a [[r generic type]] can be implemented as follows
- at [[r compile time]] the [[r compiler]] creates multiple versions of the functions for all [[r data type]] of values it is used for 

```rust
fn identity<T>(x: T) -> T { x }

let a = identity(10);                // T = i32
let b = identity(String::from("x")); // T = String
```

#### constraints
- it's possible to define contains, like in this example the [[r data type]] has to implement the [[r trait]] `XYZ` or otherwise it won't compile

```rust
fn identity<T: XYZ>(x: T) -> T {
    x // valid only for types that implement XYZ
}
```

- the constraints can be made explicit like in the following equivalent example

```rust
fn identity<T>(x: T) -> T
where
    T: XYZ,
{
    x
}
```

Tags: code rust
<!--ID: 1756383003753-->
END


START
Basic
[[rust]] example: write a [[r function]] that take two instances of arbitrary [[r data type]] and return a tuple (types might be different)
Back: 

### multiple generic types
- It's possible to have multiple [[r generic type]]
- this means `T: std::ops::Add<Output = T>` the input [[r data type]] has to implement the `Add` [[r trait]] and `T` is the [[r data type]] of the output of the add operation

```rust
fn pair<A, B>(a: A, b: B) -> (A, B) { (a, b) }
let i=1;
let j=10;
pair(j, i)
```
## generic type
- [[r function]] that work with a [[r generic type]] can be implemented as follows
- at [[r compile time]] the [[r compiler]] creates multiple versions of the functions for all [[r data type]] of values it is used for 

```rust
fn identity<T>(x: T) -> T { x }

let a = identity(10);                // T = i32
let b = identity(String::from("x")); // T = String
```

#### constraints
- it's possible to define contains, like in this example the [[r data type]] has to implement the [[r trait]] `XYZ` or otherwise it won't compile

```rust
fn identity<T: XYZ>(x: T) -> T {
    x // valid only for types that implement XYZ
}
```

- the constraints can be made explicit like in the following equivalent example

```rust
fn identity<T>(x: T) -> T
where
    T: XYZ,
{
    x
}
```

Tags: code rust

END


START
Basic
What does this mean?

```rust
fn my_funct<T: std::ops::Add<Output = T>, U: std::ops::Add<Output = U>>(x: T, y: T, u: U, v: U) -> (T, U) {...}
```

Back: 

- this means `T: std::ops::Add<Output = T>` the input [[r data type]] has to implement the `Add` [[r trait]] and `T` is the [[r data type]] of the output of the add operation

```rust
fn add_all<T: std::ops::Add<Output = T>, U: std::ops::Add<Output = U>>(x: T, y: T, u: U, v: U) -> (T, U) {
    (x + y, u + v)
}
```

## generic type
- [[r function]] that work with a [[r generic type]] can be implemented as follows
- at [[r compile time]] the [[r compiler]] creates multiple versions of the functions for all [[r data type]] of values it is used for 

```rust
fn identity<T>(x: T) -> T { x }

let a = identity(10);                // T = i32
let b = identity(String::from("x")); // T = String
```

#### constraints
- it's possible to define contains, like in this example the [[r data type]] has to implement the [[r trait]] `XYZ` or otherwise it won't compile

```rust
fn identity<T: XYZ>(x: T) -> T {
    x // valid only for types that implement XYZ
}
```

- the constraints can be made explicit like in the following equivalent example

```rust
fn identity<T>(x: T) -> T
where
    T: XYZ,
{
    x
}
```




Tags: code rust
<!--ID: 1756383003756-->
END