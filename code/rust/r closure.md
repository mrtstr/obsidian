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


# anki

START
Basic
[[r closure]] summary
- concept and syntax
- how does it interact with its environment
- how is attribute [ownership] handled

Back: 
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


Tags: code rust
<!--ID: 1756386918781-->
END