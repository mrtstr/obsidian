### vec
- fixed size collection of values with homogeneous [[r data type]]
- lives on the [[li stack]] (its values too)
- can be defined as mutable or immutable, but the size can't change even if mutable
- the mutability of its values depends on their [[r data type]]
- a [[py list comprehension]] style definition does not work → use [[r vec]] instead
- support [[r slicing]]
#### syntax
##### declaration using hard coded values
- can be declared with fixed values using `[]`

```rust
let arr = [1, 2, 3];
let mut marr  = [1, 2, 3];
marr[0] = 10
arr[0] = 10; // error

// two dimensional
let matrix: [[i32; 3]; 2] = [
	[1, 2, 3], 
	[4, 5, 6],
];
```

##### declaration with the same values

- can be initialized with the same values using the following syntax

```rust
let arr = [0; 5]; // [0, 0, 0, 0, 0]

```

##### declaration from closure
- can be declared with `std::array::from_fn` that takes a closure when the number of elements is known at [[r compile time]]

```rust
let arr: [i32; 10] = std::array::from_fn(|i| i as i32);
let m: [[i32; 3]; 3] =
	std::array::from_fn(|r|                     // r: 0..3
		std::array::from_fn(|c|                 // c: 0..3
			(r as i32) * 3 + (c as i32)
		)
	);
```

##### multidimensional arrays
- multidimensional [[r array]] can be defined as follows with the [[r data type]] annotation would look like `[[i32; 3]; 2]`

```rust
// hardcoded values
let matrix: [[i32; 3]; 2] = [
	[1, 2, 3], 
	[4, 5, 6],
];

// init with constant
let matrix: [[i32; 3]; 2] = [[1; 3]; 2]; 
```

##### accessing elements
- elements can be accessed using `arr[i]`

```rust
arr[1] = 10;
let i = 2
arr[i] = 3.14;
```