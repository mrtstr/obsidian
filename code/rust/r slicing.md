### slicing
- selecting from a specific connected part from a [[r container]]
- supported for example by [[r array]], [[r vec]], [[r string]]

```rust
let arr = [10, 20, 30, 40, 50];
let slice = &arr[1..4];  // elements at index 1,2,3
println!("{:?}", slice); // [20, 30, 40]
```


- out of the box options
```rust
&thing[start..end]   // half-open range [start, end)
&thing[..end]        // from start to end-1
&thing[start..]      // from start to the end
&thing[..]           // whole slice
```

- slicing relative to the end
```python
s = "hello"
print(s[0:-1])   # "hell"
```

```rust
let s = String::from("hello");
let slice = &s[0..s.len()-1];
println!("{}", slice); // "hell"
```

- mutable borrowing works like the following

```rust
{
	let mut arr = [10, 20, 30, 40, 50];
	let slice = &mut arr[1..4];
	slice[1] = 1000;
	println!("{:?}", slice);
	println!("{:?}", arr);
}
```

```rust
{
	let mut arr = [10, 20, 30, 40, 50];
	{
		let slice = &mut arr[1..4];
		slice[2] = 2000;
	}
	arr[1] = 1000; // works because the mut 
	// borrow is alreay dropped
	println!("{:?}", arr);
}
```

```rust
{
	let mut arr = [10, 20, 30, 40, 50];
	let slice = &mut arr[1..4]; // elements at index 1,2,3
	arr[1] = 1000; // does not work because mutable 
	// borrows prevent the manuputatin of the original data
	println!("{:?}", slice);
	println!("{:?}", arr);
}
```

```rust
{
	let mut arr = [10, 20, 30, 40, 50];
	let mut slice = &arr[1..4]; // does not work
	// because the data is not mut borrowed
	// the mut of the slice is just about 
	//the the locations it points to
	slice[1] = 1000;
	println!("{:?}", slice);
	println!("{:?}", arr);
}
```

# anki

START
Basic
[[r slicing]] in [[rust]]
- where can it be used
- syntax
- 4 out of the box options
- example mutable [[r slicing]]
- slicing relative to the end
Back: 
### slicing
- selecting from a specific connected part from a [[r container]]
- supported for example by [[r array]], [[r vec]], [[r string]]

```rust
let arr = [10, 20, 30, 40, 50];
let slice = &arr[1..4];  // elements at index 1,2,3
println!("{:?}", slice); // [20, 30, 40]
```


- out of the box options
```rust
&thing[start..end]   // half-open range [start, end)
&thing[..end]        // from start to end-1
&thing[start..]      // from start to the end
&thing[..]           // whole slice
```

- slicing relative to the end
```python
s = "hello"
print(s[0:-1])   # "hell"
```

```rust
let s = String::from("hello");
let slice = &s[0..s.len()-1];
println!("{}", slice); // "hell"
```

- mutable borrowing works like the following

```rust
{
	let mut arr = [10, 20, 30, 40, 50];
	let slice = &mut arr[1..4];
	slice[1] = 1000;
	println!("{:?}", slice);
	println!("{:?}", arr);
}
```

```rust
{
	let mut arr = [10, 20, 30, 40, 50];
	{
		let slice = &mut arr[1..4];
		slice[2] = 2000;
	}
	arr[1] = 1000; // works because the mut 
	// borrow is alreay dropped
	println!("{:?}", arr);
}
```

```rust
{
	let mut arr = [10, 20, 30, 40, 50];
	let slice = &mut arr[1..4]; // elements at index 1,2,3
	arr[1] = 1000; // does not work because mutable 
	// borrows prevent the manuputatin of the original data
	println!("{:?}", slice);
	println!("{:?}", arr);
}
```

```rust
{
	let mut arr = [10, 20, 30, 40, 50];
	let mut slice = &arr[1..4]; // does not work
	// because the data is not mut borrowed
	// the mut of the slice is just about 
	//the the locations it points to
	slice[1] = 1000;
	println!("{:?}", slice);
	println!("{:?}", arr);
}
```
Tags: code rust
<!--ID: 1756627337941-->
END


START
Basic
what is wrong with the following examples and how to fix it

```rust
{
	let mut arr = [10, 20, 30, 40, 50];
	let slice = &mut arr[1..4];
	arr[1] = 1000;
	println!("{:?}", slice);
	println!("{:?}", arr);
}
```

```rust
{
	let mut arr = [10, 20, 30, 40, 50];
	let mut slice = &arr[1..4];
	slice[1] = 1000;
	println!("{:?}", slice);
	println!("{:?}", arr);
}
```

```rust
{
	let mut arr = [10, 20, 30, 40, 50];
	{
		let slice = &mut arr[1..4];
		slice[2] = 2000;
	}
	arr[1] = 1000;
	println!("{:?}", arr);
}
```

Back: 
### slicing
- selecting from a specific connected part from a [[r container]]
- supported for example by [[r array]], [[r vec]], [[r string]]

```rust
let arr = [10, 20, 30, 40, 50];
let slice = &arr[1..4];  // elements at index 1,2,3
println!("{:?}", slice); // [20, 30, 40]
```


- out of the box options
```rust
&thing[start..end]   // half-open range [start, end)
&thing[..end]        // from start to end-1
&thing[start..]      // from start to the end
&thing[..]           // whole slice
```

- slicing relative to the end
```python
s = "hello"
print(s[0:-1])   # "hell"
```

```rust
let s = String::from("hello");
let slice = &s[0..s.len()-1];
println!("{}", slice); // "hell"
```

- mutable borrowing works like the following

```rust
{
	let mut arr = [10, 20, 30, 40, 50];
	let slice = &mut arr[1..4];
	slice[1] = 1000;
	println!("{:?}", slice);
	println!("{:?}", arr);
}
```

```rust
{
	let mut arr = [10, 20, 30, 40, 50];
	{
		let slice = &mut arr[1..4];
		slice[2] = 2000;
	}
	arr[1] = 1000; // works because the mut 
	// borrow is alreay dropped
	println!("{:?}", arr);
}
```

```rust
{
	let mut arr = [10, 20, 30, 40, 50];
	let slice = &mut arr[1..4]; // elements at index 1,2,3
	arr[1] = 1000; // does not work because mutable 
	// borrows prevent the manuputatin of the original data
	println!("{:?}", slice);
	println!("{:?}", arr);
}
```

```rust
{
	let mut arr = [10, 20, 30, 40, 50];
	let mut slice = &arr[1..4]; // does not work
	// because the data is not mut borrowed
	// the mut of the slice is just about 
	//the the locations it points to
	slice[1] = 1000;
	println!("{:?}", slice);
	println!("{:?}", arr);
}
```
Tags: code rust
<!--ID: 1756627337943-->
END