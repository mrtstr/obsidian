
## functions as arguments
- [[r function]] and [[r closure]] are first class citizens and can be passed as arguments like in the following examples

```rust
fn square_func(x: i32) -> i32 { x * x }

fn apply_func(f: fn(i32) -> i32, n: i32) -> i32 {
    f(n)
}
fn apply_closure<F: Fn(i32) -> i32>(f: F, n: i32) -> i32
{
    f(n)
}
fn main() {
	let square_clos = |x| x * x;
	println!("{}", apply_func(square_func, 4)); // 16
	println!("{}", apply_closure(square_clos, 4)); // 16
}
```

- when a [[r closure]] is passed as a function parameter we need to define which [[r trait]] of `Fn`, `FnMut` and `FnOnce` it implements and [[rust]] cannot take a [[r trait]] directly as a parameter type
- this means we need to define the [[r function]] for a [[r generic type]]

# ---------------

![[r closure#closure]]

![[r generic type#generic type]]

# anki

START
Basic
- write a [[r function]] that applies the square function to an int and a function that applied the square closure to an input

```rust
fn square_func(x: i32) -> i32 { x * x }
let square_clos = |x| x * x;
```

- what is the difference?

Back: 
## functions as arguments
- [[r function]] and [[r closure]] are first class citizens and can be passed as arguments like in the following examples

```rust
fn square_func(x: i32) -> i32 { x * x }

fn apply_func(f: fn(i32) -> i32, n: i32) -> i32 {
    f(n)
}
fn apply_closure<F: Fn(i32) -> i32>(f: F, n: i32) -> i32
{
    f(n)
}
fn main() {
	let square_clos = |x| x * x;
	println!("{}", apply_func(square_func, 4)); // 16
	println!("{}", apply_closure(square_clos, 4)); // 16
}
```

- when a [[r closure]] is passed as a function parameter we need to define which [[r trait]] of `Fn`, `FnMut` and `FnOnce` it implements and [[rust]] cannot take a [[r trait]] directly as a parameter type
- this means we need to define the [[r function]] for a [[r generic type]]


________________

## closure
- anonymous [[r function]] like a [[py lambda functions]] in [[python]]

```rust
let add = |x: i32, y: i32| -> i32 { x + y };
println!("{}", add(2, 3)); // 5
```

- [[r closure]] can capture variables from outside their [[r scope]] by immutual borrow
### environment interaction
- [[r closure]] can capture variables from outside their [[r scope]] like in the following example
- depending on the context [[rust]] decides whether to take [[r ownership]], borrow it mutable or immutable depending on if its changed or replaced in the [[r closure]]

```rust
fn main() {
    let factor = 2;
    let multiply = |x: i32| x * factor; 
    // captures `factor` as immutable borrow
    println!("{}", multiply(5)); // 10
    
	let mut sum = 0;
	let mut add = |x: i32| { sum += x; };  // writes -> &mut sum
	// captures `factor` as mutable borrow
    
}
```

### attribute ownership
- [[rust]] decides automatically between the following options if [[r ownership]] of its parameters is taken depending on how its called
	- `Fn`: **Borrow** `x` if like `|x| x + factor`
	- `FnMut`: **Mutable borrow** `x` if like `|x| count += x`
	- `FnOnce`: **Move** (taking ownership of `x`) if like `|x| vec.push(x)`

- for each of the 3 options one of the [[r trait]] `Fn`, `FnMut`, `FnOnce` is implemented


## generic type
- [[r function]] that work with a [[r generic type]] can be implemented as follows
- at [[r compile time]] the [[r rustc]] creates multiple versions of the functions for all [[r data type]] of values it is used for 

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
<!--ID: 1756386918777-->
END
