### reference
- in [[rust]] a [[r reference]] is a [[r pointer]] that borrows the data (it doesn't take [[r ownership]])
	→ its a non owning pointer to the [[li heap]] address 
- the `&` operator reads the memory address (= [[r reference]]) from and [[r variable]] (the opposite operation is dereferencing with `*`)
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

![[Pasted image 20250929153637.png]]

# anki

START
Basic
[[r reference]] in [[rust]]
- concept
- how to declare it
- two rules that apply
- how is it often used

Back: 
### reference
- in [[rust]] a [[r reference]] is a [[r pointer]] that borrows the data (it doesn't take [[r ownership]])
	→ its a non owning pointer to the [[li heap]] address 
- the `&` operator reads the memory address (= [[r reference]]) from and [[r variable]] (the opposite operation is dereferencing with `*`)
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

![[Pasted image 20250929153716.png]]
Tags: code rust
<!--ID: 1756052658821-->
END

