## iterator
- in [[rust]] and [[r iterator]] implements the following [[r trait]]:

```rust
trait Iterator {
    type Item;
    fn next(&mut self) -> Option<Self::Item>;
}
```
- implements the following two functions
	- **`Item`**: the type of element it yields.
	- **`next()`**: returns `Some(item)` until iteration ends, then `None`.

### creating iterators
- can be created from a [[r container]] with one of the 3 following functions
	- `.iter()` → yields `&T` (immutable references)
	- `.iter_mut()` → yields `&mut T` (mutable references)
	- `.into_iter()` → yields `T` (takes ownership, consumes the collection)

```rust
let v = vec![10, 20, 30];
let mut iter = v.iter();    // creates an iterator over &i32

println!("{:?}", iter.next()); // Some(&10)
println!("{:?}", iter.next()); // Some(&20)
println!("{:?}", iter.next()); // Some(&30)
println!("{:?}", iter.next()); // None
```

- [[rust]] does not have `yield` but It's possible to create an [[r struct]] and implement the [[r trait]]

```rust
struct Counter {
    count: u32,
}

impl Counter {
    fn new() -> Self {
        Counter { count: 0 }
    }
}

impl Iterator for Counter {
    type Item = u32;

    fn next(&mut self) -> Option<Self::Item> {
        if self.count < 5 {
            self.count += 1;
            Some(self.count)
        } else {
            None
        }
    }
}
```
### consumers
the following functions take [[r iterator]] and return something else / do something with it
- `collect()` → turn into `Vec`, `HashSet`, etc.
- `sum()`, `product()` → arithmetic reductions
- `fold(init, f)` → accumulate manually
- `count()` → number of items
- `any()`, `all()` → logical checks that return a bool
- `find()` → first element matching predicate
- `for_each()` → run a function on each element (side effects)

```rust
(1..10).find(|&x| x % 2 == 0)
// Some(2)
```
### lazy adaptors

Methods that **return a new iterator** (they don’t consume items yet):
- `map` → transform each element
- `filter` → keep only elements matching a predicate
- `enumerate` → yields `(index, item)`
- `take(n)` → first `n` elements
- `skip(n)` → skip first `n` elements
- `chain` → concatenate two iterators
- `zip` → combine two iterators

```rust
let v: Vec<i32> = (1..10)
	.filter(|&x| x % 2 == 0)
	.map(|x| x * x)
	.collect();
// [4, 16, 36, 64]
```

```rust
let v: Vec<i32> = (1..4).chain(10..13).collect();
// [1, 2, 3, 10, 11, 12]
```

```rust
let v: Vec<(i32, i32)> = (1..4).zip(10..13).collect();
// [(1, 10), (2, 11), (3, 12)]
```


```rust
let v: Vec<i32> = (1..10)
	.skip(2)
	.take(4)
	.collect();
// [3, 4, 5, 6]
```


# anki

START
Basic
[[r iterator]] in [[rust]]
- concept: what is it and its properties
- how to create it from a [[r container]] (3 with difference)
- how to define a general one
- consumers concept with examples (7)
- adaptors concept with examples (7)
Back: 
## iterator
- in [[rust]] and [[r iterator]] implements the following [[r trait]]:

```rust
trait Iterator {
    type Item;
    fn next(&mut self) -> Option<Self::Item>;
}
```
- implements the following two functions
	- **`Item`**: the type of element it yields.
	- **`next()`**: returns `Some(item)` until iteration ends, then `None`.

### creating iterators
- can be created from a [[r container]] with one of the 3 following functions
	- `.iter()` → yields `&T` (immutable references)
	- `.iter_mut()` → yields `&mut T` (mutable references)
	- `.into_iter()` → yields `T` (takes ownership, consumes the collection)

```rust
let v = vec![10, 20, 30];
let mut iter = v.iter();    // creates an iterator over &i32

println!("{:?}", iter.next()); // Some(&10)
println!("{:?}", iter.next()); // Some(&20)
println!("{:?}", iter.next()); // Some(&30)
println!("{:?}", iter.next()); // None
```

- [[rust]] does not have `yield` but It's possible to create an [[r struct]] and implement the [[r trait]]

```rust
struct Counter {
    count: u32,
}

impl Counter {
    fn new() -> Self {
        Counter { count: 0 }
    }
}

impl Iterator for Counter {
    type Item = u32;

    fn next(&mut self) -> Option<Self::Item> {
        if self.count < 5 {
            self.count += 1;
            Some(self.count)
        } else {
            None
        }
    }
}
```
### consumers
the following functions take [[r iterator]] and return something else / do something with it
- `collect()` → turn into `Vec`, `HashSet`, etc.
- `sum()`, `product()` → arithmetic reductions
- `fold(init, f)` → accumulate manually
- `count()` → number of items
- `any()`, `all()` → logical checks that return a bool
- `find()` → first element matching predicate
- `for_each()` → run a function on each element (side effects)

```rust
(1..10).find(|&x| x % 2 == 0)
// Some(2)
```
### lazy adaptors

Methods that **return a new iterator** (they don’t consume items yet):
- `map` → transform each element
- `filter` → keep only elements matching a predicate
- `enumerate` → yields `(index, item)`
- `take(n)` → first `n` elements
- `skip(n)` → skip first `n` elements
- `chain` → concatenate two iterators
- `zip` → combine two iterators

```rust
let v: Vec<i32> = (1..10)
	.filter(|&x| x % 2 == 0)
	.map(|x| x * x)
	.collect();
// [4, 16, 36, 64]
```

```rust
let v: Vec<i32> = (1..4).chain(10..13).collect();
// [1, 2, 3, 10, 11, 12]
```

```rust
let v: Vec<(i32, i32)> = (1..4).zip(10..13).collect();
// [(1, 10), (2, 11), (3, 12)]
```


```rust
let v: Vec<i32> = (1..10)
	.skip(2)
	.take(4)
	.collect();
// [3, 4, 5, 6]
```

Tags: code rust
<!--ID: 1756651829333-->
END


START
Basic
[[r iterator]] in [[rust]] examples
- create an [[r iterator]] over the squared numbers from 1 to 10 that are even
- given an [[r iterator]] create an [[r vec]] that contains its 3rd, 4th, 5th and 6th number
Back: 

```rust
let v: Vec<i32> = (1..10)
	.filter(|&x| x % 2 == 0)
	.map(|x| x * x)
	.collect();
// [4, 16, 36, 64]
```

```rust
let v: Vec<i32> = (1..10)
	.skip(2)
	.take(4)
	.collect();
// [3, 4, 5, 6]
```
## iterator
- in [[rust]] and [[r iterator]] implements the following [[r trait]]:

```rust
trait Iterator {
    type Item;
    fn next(&mut self) -> Option<Self::Item>;
}
```
- implements the following two functions
	- **`Item`**: the type of element it yields.
	- **`next()`**: returns `Some(item)` until iteration ends, then `None`.

### creating iterators
- can be created from a [[r container]] with one of the 3 following functions
	- `.iter()` → yields `&T` (immutable references)
	- `.iter_mut()` → yields `&mut T` (mutable references)
	- `.into_iter()` → yields `T` (takes ownership, consumes the collection)

```rust
let v = vec![10, 20, 30];
let mut iter = v.iter();    // creates an iterator over &i32

println!("{:?}", iter.next()); // Some(&10)
println!("{:?}", iter.next()); // Some(&20)
println!("{:?}", iter.next()); // Some(&30)
println!("{:?}", iter.next()); // None
```

- [[rust]] does not have `yield` but It's possible to create an [[r struct]] and implement the [[r trait]]

```rust
struct Counter {
    count: u32,
}

impl Counter {
    fn new() -> Self {
        Counter { count: 0 }
    }
}

impl Iterator for Counter {
    type Item = u32;

    fn next(&mut self) -> Option<Self::Item> {
        if self.count < 5 {
            self.count += 1;
            Some(self.count)
        } else {
            None
        }
    }
}
```
### consumers
the following functions take [[r iterator]] and return something else / do something with it
- `collect()` → turn into `Vec`, `HashSet`, etc.
- `sum()`, `product()` → arithmetic reductions
- `fold(init, f)` → accumulate manually
- `count()` → number of items
- `any()`, `all()` → logical checks that return a bool
- `find()` → first element matching predicate
- `for_each()` → run a function on each element (side effects)

```rust
(1..10).find(|&x| x % 2 == 0)
// Some(2)
```
### lazy adaptors

Methods that **return a new iterator** (they don’t consume items yet):
- `map` → transform each element
- `filter` → keep only elements matching a predicate
- `enumerate` → yields `(index, item)`
- `take(n)` → first `n` elements
- `skip(n)` → skip first `n` elements
- `chain` → concatenate two iterators
- `zip` → combine two iterators



```rust
let v: Vec<i32> = (1..4).chain(10..13).collect();
// [1, 2, 3, 10, 11, 12]
```

```rust
let v: Vec<(i32, i32)> = (1..4).zip(10..13).collect();
// [(1, 10), (2, 11), (3, 12)]
```




Tags: code rust
<!--ID: 1756651829336-->
END


START
Basic
[[r iterator]] in [[rust]] examples
- create the following [[r vec]]: `[1, 2, 3, 10, 11, 12]`
- create the following [[r vec]]: `[(1, 10), (2, 11), (3, 12)]`
- given a [[r iterator]]: return the first even number

Back: 


```rust
let v: Vec<i32> = (1..4).chain(10..13).collect();
// [1, 2, 3, 10, 11, 12]
```

```rust
let v: Vec<(i32, i32)> = (1..4).zip(10..13).collect();
// [(1, 10), (2, 11), (3, 12)]
```


```rust
(1..10).find(|&x| x % 2 == 0)
// Some(2)
```
## iterator
- in [[rust]] and [[r iterator]] implements the following [[r trait]]:

```rust
trait Iterator {
    type Item;
    fn next(&mut self) -> Option<Self::Item>;
}
```
- implements the following two functions
	- **`Item`**: the type of element it yields.
	- **`next()`**: returns `Some(item)` until iteration ends, then `None`.

### creating iterators
- can be created from a [[r container]] with one of the 3 following functions
	- `.iter()` → yields `&T` (immutable references)
	- `.iter_mut()` → yields `&mut T` (mutable references)
	- `.into_iter()` → yields `T` (takes ownership, consumes the collection)

```rust
let v = vec![10, 20, 30];
let mut iter = v.iter();    // creates an iterator over &i32

println!("{:?}", iter.next()); // Some(&10)
println!("{:?}", iter.next()); // Some(&20)
println!("{:?}", iter.next()); // Some(&30)
println!("{:?}", iter.next()); // None
```

- [[rust]] does not have `yield` but It's possible to create an [[r struct]] and implement the [[r trait]]

```rust
struct Counter {
    count: u32,
}

impl Counter {
    fn new() -> Self {
        Counter { count: 0 }
    }
}

impl Iterator for Counter {
    type Item = u32;

    fn next(&mut self) -> Option<Self::Item> {
        if self.count < 5 {
            self.count += 1;
            Some(self.count)
        } else {
            None
        }
    }
}
```
### consumers
the following functions take [[r iterator]] and return something else / do something with it
- `collect()` → turn into `Vec`, `HashSet`, etc.
- `sum()`, `product()` → arithmetic reductions
- `fold(init, f)` → accumulate manually
- `count()` → number of items
- `any()`, `all()` → logical checks that return a bool
- `find()` → first element matching predicate
- `for_each()` → run a function on each element (side effects)

```rust
(1..10).find(|&x| x % 2 == 0)
// Some(2)
```
### lazy adaptors

Methods that **return a new iterator** (they don’t consume items yet):
- `map` → transform each element
- `filter` → keep only elements matching a predicate
- `enumerate` → yields `(index, item)`
- `take(n)` → first `n` elements
- `skip(n)` → skip first `n` elements
- `chain` → concatenate two iterators
- `zip` → combine two iterators

```rust
let v: Vec<i32> = (1..10)
	.filter(|&x| x % 2 == 0)
	.map(|x| x * x)
	.collect();
// [4, 16, 36, 64]
```



```rust
let v: Vec<i32> = (1..10)
	.skip(2)
	.take(4)
	.collect();
// [3, 4, 5, 6]
```

Tags: code rust
<!--ID: 1756651829338-->
END