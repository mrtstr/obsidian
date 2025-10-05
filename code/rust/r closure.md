## closure
- anonymous [[r function]] like a [[py lambda functions]] in [[python]]

```rust
let add = |x: i32, y: i32| -> i32 { x + y };
println!("{}", add(2, 3)); // 5
```

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

### functions that return closures
- we can define a function that returns a [[r closure]] by type annotating the [[r trait]] of closures

```rust
fn returns_closure() -> impl Fn(i32) -> i32 {
    |x| x + 1
}
println!("{}", returns_closure()(2));
// 2
```

- when we want to bake a value in the [[r closure]] we need [[r box]] because the size of the closure is not known at compile time

```rust
fn returns_initialized_closure(init: i32) -> Box<dyn Fn(i32) -> i32> {
    Box::new(move |x| x + init)
}
println!("{}", (*returns_initialized_closure(4))(2)); //explicit deref
// println!("{}", returns_initialized_closure(4)(2)); // implicit deref
// 6
```
# anki

START
Basic
[[r closure]] summary
- concept and syntax
- how does it interact with its environment
- how is attribute [[r ownership]] handled
- which [[r trait]] do they implement?
- functions that return a [[r closure]]
Back: 
## closure
- anonymous [[r function]] like a [[py lambda functions]] in [[python]]

```rust
let add = |x: i32, y: i32| -> i32 { x + y };
println!("{}", add(2, 3)); // 5
```

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

### functions that return closures
- we can define a function that returns a [[r closure]] by type annotating the [[r trait]] of closures

```rust
fn returns_closure() -> impl Fn(i32) -> i32 {
    |x| x + 1
}
println!("{}", returns_closure()(2));
// 2
```

- when we want to bake a value in the [[r closure]] we need [[r box]] because the size of the closure is not known at compile time

```rust
fn returns_initialized_closure(init: i32) -> Box<dyn Fn(i32) -> i32> {
    Box::new(move |x| x + init)
}
println!("{}", (*returns_initialized_closure(4))(2)); //explicit deref
// println!("{}", returns_initialized_closure(4)(2)); // implicit deref
// 6
```

Tags: code rust
<!--ID: 1756386918781-->
END


START
Basic
- sort the [[r array]] of rectangles by their width

```rust
struct Rectangle {
    width: u32,
    height: u32,
}

fn main() {
    let mut list = [
        Rectangle { width: 10, height: 1 },
        Rectangle { width: 3, height: 5 },
        Rectangle { width: 7, height: 12 },
    ];
}
```

Back: 

```rust
struct Rectangle {
    width: u32,
    height: u32,
}

fn main() {
    let mut list = [
        Rectangle { width: 10, height: 1 },
        Rectangle { width: 3, height: 5 },
        Rectangle { width: 7, height: 12 },
    ];

    list.sort_by_key(|r| r.width);
    println!("{list:#?}");
}
```

Tags: code rust
<!--ID: 1759603319837-->
END


START
Basic
write a [[r function]] that returns a [[r closure]]
1) normal case
2) the functions moves values in the closure to customize its behavior

Back: 
### functions that return closures
- we can define a function that returns a [[r closure]] by type annotating the [[r trait]] of closures

```rust
fn returns_closure() -> impl Fn(i32) -> i32 {
    |x| x + 1
}
println!("{}", returns_closure()(2));
// 2
```

- when we want to bake a value in the [[r closure]] we need [[r box]] because the size of the closure is not known at compile time

```rust
fn returns_initialized_closure(init: i32) -> Box<dyn Fn(i32) -> i32> {
    Box::new(move |x| x + init)
}
println!("{}", (*returns_initialized_closure(4))(2)); //explicit deref
// println!("{}", returns_initialized_closure(4)(2)); // implicit deref
// 6
```

## closure
- anonymous [[r function]] like a [[py lambda functions]] in [[python]]

```rust
let add = |x: i32, y: i32| -> i32 { x + y };
println!("{}", add(2, 3)); // 5
```

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


Tags: code rust
<!--ID: 1759683035830-->
END