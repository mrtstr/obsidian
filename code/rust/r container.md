### container
- a container is any data structure that hold multiple elements with homogeneous
- standard [[r container]] live in `std::collections`
- share the [[r iterator]] API
- can be purely on the [[li stack]] like [[r array]] or be a [[r smart pointer]] that manages the data on the [[li heap]]

- [[r vec]]
- [[r array]]
- [[r hash map]]
- [[r tuple]] is not a [[r container]] because it has heterogeneous [[r data type]] and does not support the [[r iterator]] API
# --------------

![[r tuple#tuple]]

![[r hash map#hash map]]


![[r vec#vec]]

![[r array#array]]




# anki


START
Basic
[[r container]] in [[rust]]
- concept
- examples
- is a [[r tuple]] as [[r container]]
Back: 

### container
- a container is any data structure that hold multiple elements with homogeneous
- standard [[r container]] live in `std::collections`
- share the [[r iterator]] API
- can be purely on the [[li stack]] like [[r array]] or be a [[r smart pointer]] that manages the data on the [[li heap]]

- [[r vec]]
- [[r array]]
- [[r hash map]]
- [[r tuple]] is not a [[r container]] because it has heterogeneous [[r data type]] and does not support the [[r iterator]] API

Tags: code rust
<!--ID: 1756570478752-->
END



START
Basic
when to use a [[r array]] and when a [[r vec]]?
- conceptual differences regarding 
	- memory management
	- speed
	- overhead

Back: 
- If the number of elements is **constant and small** → use **array**.
- If the number of elements is **dynamic, large, or unknown at compile time** → use **Vec**.

|Feature|Array `[T; N]`|Vec|
|---|---|---|
|Size|Fixed at compile time|Dynamic at runtime|
|Memory|Stack (inline)|Heap (pointer + len + cap)|
|Type|Length is part of type|Length not in type|
|Mutability of size|Immutable length|Grow/shrink with push/pop|
|Performance|No allocation, fast|Slight overhead from heap|
|Typical usage|Small, fixed-size data|Dynamic collections|

### array
- fixed size collection of values with homogeneous [[r data type]]
- lives on the [[li stack]] (its values too)
- can be defined as mutable or immutable, but the size can't change even if mutable
- the mutability of its values depends on their [[r data type]]
- a [[py list comprehension]] style definition does not work → use [[r vec]] instead
- support [[r slicing]]


### vec
- [[r smart pointer]] on the stack that points to a and contains the values with homogeneous [[r data type]]
-  the buffer on the [[li heap]] can grow and shrink dynamically
- can be mutable or immutable
- supports [[r iterator]] and [[r range]]

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


Tags: code rust
<!--ID: 1756570478756-->
END