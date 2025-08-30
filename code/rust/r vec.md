### vec
- [[r smart pointer]] on the stack that points to a and contains the values with homogeneous [[r data type]]
-  the buffer on the [[li heap]] can grow and shrink dynamically
- can be mutable or immutable
- supports [[r iterators]] and [[r range]]

```rust
Vec<T> (on stack)
 ├─ ptr: *mut T   (pointer to first element on the heap)
 ├─ len: usize    (number of elements in use)
 └─ cap: usize    (how many elements can fit before reallocation)

Heap (owned buffer)
 └─ [elem0, elem1, elem2, ...]
```

#### memory management
- the allocated memory is saved as `cap` and the current used memory is saved as `len`
- when `cap` is not sufficient new memory is requested from the [[r global allocator]] by usually doubling it current `cap`
- two possible cases:
	1) **In-place growth possible**: extend the current space when possible → $\mathcal{O}(1)$ 
	2) **In-place growth not possible**: allocate a new buffer when old buffer cant be extended → $\mathcal{O}(cap)$
- when the final size is known `Vec::with_capacity(size)` can be used to make it more efficient

#### syntax
- can be declared empty or filled directly using the [[r macro]] and the normal [[r array]] syntax

```rust
let mut v: Vec<i32> = Vec::new();
let mut v = vec![1, 2, 3];  // type Vec<i32>
let mut v = vec![0; 5];  // [0, 0, 0, 0, 0]
```

- extending with a single values and accessing data

```rust
v.push(44); // extend
v[2] = 33; // redefine an existing value
```

- 3 methods for combining two [[r vec]]:

```rust
let mut v1 = vec![1,2,3];
let mut v2 = vec![4,5,6];
v1.extend(v2); 
// pushes element by element and consumes `v2`
// O(m)
v1.append(&mut v2); 
// copies compled block of v2 to v1 and 
// v2 still exist but is empty
// O(1)
let v3 = [v1, v2].concat();      // consumes both
let v3 = [&v1[..], &v2[..]].concat(); // borrows
// O(n + m)
```
# anki


START
Basic
[[r vec]]
- concept and memory management
- how expensive is extending and how can it be reduced?

syntax
- how to create it (3)
- how to  access values
- how to combine two [[r vec]] (3 ways with difference)
Back: 
### vec
- [[r smart pointer]] on the stack that points to a and contains the values with homogeneous [[r data type]]
-  the buffer on the [[li heap]] can grow and shrink dynamically
- can be mutable or immutable
- supports [[r iterators]] and [[r range]]

```rust
Vec<T> (on stack)
 ├─ ptr: *mut T   (pointer to first element on the heap)
 ├─ len: usize    (number of elements in use)
 └─ cap: usize    (how many elements can fit before reallocation)

Heap (owned buffer)
 └─ [elem0, elem1, elem2, ...]
```

#### memory management
- the allocated memory is saved as `cap` and the current used memory is saved as `len`
- when `cap` is not sufficient new memory is requested from the [[r global allocator]] by usually doubling it current `cap`
- two possible cases:
	1) **In-place growth possible**: extend the current space when possible → $\mathcal{O}(1)$ 
	2) **In-place growth not possible**: allocate a new buffer when old buffer cant be extended → $\mathcal{O}(cap)$
- when the final size is known `Vec::with_capacity(size)` can be used to make it more efficient

#### syntax
- can be declared empty or filled directly using the [[r macro]] and the normal [[r array]] syntax

```rust
let mut v: Vec<i32> = Vec::new();
let mut v = vec![1, 2, 3];  // type Vec<i32>
let mut v = vec![0; 5];  // [0, 0, 0, 0, 0]
```

- extending with a single values and accessing data

```rust
v.push(44); // extend
v[2] = 33; // redefine an existing value
```

- 3 methods for combining two [[r vec]]:

```rust
let mut v1 = vec![1,2,3];
let mut v2 = vec![4,5,6];
v1.extend(v2); 
// pushes element by element and consumes `v2`
// O(m)
v1.append(&mut v2); 
// copies compled block of v2 to v1 and 
// v2 still exist but is empty
// O(1)
let v3 = [v1, v2].concat();      // consumes both
let v3 = [&v1[..], &v2[..]].concat(); // borrows
// O(n + m)
```

Tags: code rust
<!--ID: 1756565350486-->
END


START
Basic
difference between the following regarding speed and side effects:

```rust
v.extend(v2); 
v.append(&mut v2); 
let v3 = [v1, v2].concat();
let v3 = [&v1[..], &v2[..]].concat();
```

Back: 


- 3 methods for combining two [[r vec]]:

```rust
let mut v1 = vec![1,2,3];
let mut v2 = vec![4,5,6];
v1.extend(v2); 
// pushes element by element and consumes `v2`
// O(m)
v1.append(&mut v2); 
// copies compled block of v2 to v1 and 
// v2 still exist but is empty
// O(1)
let v3 = [v1, v2].concat();      // consumes both
let v3 = [&v1[..], &v2[..]].concat(); // borrows
// O(n + m)
```
### vec
- [[r smart pointer]] on the stack that points to a and contains the values with homogeneous [[r data type]]
-  the buffer on the [[li heap]] can grow and shrink dynamically
- can be mutable or immutable
- supports [[r iterators]] and [[r range]]

```rust
Vec<T> (on stack)
 ├─ ptr: *mut T   (pointer to first element on the heap)
 ├─ len: usize    (number of elements in use)
 └─ cap: usize    (how many elements can fit before reallocation)

Heap (owned buffer)
 └─ [elem0, elem1, elem2, ...]
```

#### memory management
- the allocated memory is saved as `cap` and the current used memory is saved as `len`
- when `cap` is not sufficient new memory is requested from the [[r global allocator]] by usually doubling it current `cap`
- two possible cases:
	1) **In-place growth possible**: extend the current space when possible → $\mathcal{O}(1)$ 
	2) **In-place growth not possible**: allocate a new buffer when old buffer cant be extended → $\mathcal{O}(cap)$
- when the final size is known `Vec::with_capacity(size)` can be used to make it more efficient

#### syntax
- can be declared empty or filled directly using the [[r macro]] and the normal [[r array]] syntax

```rust
let mut v: Vec<i32> = Vec::new();
let mut v = vec![1, 2, 3];  // type Vec<i32>
let mut v = vec![0; 5];  // [0, 0, 0, 0, 0]
```

- extending with a single values and accessing data

```rust
v.push(44); // extend
v[2] = 33; // redefine an existing value
```



Tags: code rust
<!--ID: 1756565350491-->
END