## ndarray
- library for n dimensional array processing like [[numpy]]

### zip
- used for [[r iterator]] based element wise processing of one or more arrays
- similar to the [[r std]] zip for general [[r iterator]] but with the following differences

`std::iter::zip`
- Works on **any iterators**.
- Doesn’t know about shapes, axes, or broadcasting.
- Doesn’t give cache-friendly access to `ndarray` storage automatically.
`ndarray::Zip`
- Works on **arrays and views** (`ArrayBase`, `ArrayView`, `ArrayViewMut`).
- Understands **dimensions, strides, and broadcasting**.
- Optimizes iteration order for performance.
- Can be extended with parallel iteration via [[r rayon]]


```rust
use ndarray::{Array2, Zip};

let a = Array2::<f64>::zeros((2, 2));
let b = Array2::<f64>::ones((2, 2));

Zip::from(&a)
    .and(&b)
    .for_each(|x, y| {
        println!("{}", x + y);
    });
```

this is equivalent to the following:

```rust
use ndarray::Array2;

let a = Array2::<f64>::zeros((2, 2));
let b = Array2::<f64>::ones((2, 2));

for i in 0..2 {
    for j in 0..2 {
        println!("{}", a[[i, j]] + b[[i, j]]);
    }
}
```

#### in place update pattern

```rust
use ndarray::{Array2, Zip};

let mut out = Array2::<f64>::zeros((2, 2));
let a = Array2::<f64>::from_elem((2, 2), 2.0);
let b = Array2::<f64>::from_elem((2, 2), 3.0);

Zip::from(&mut out)
    .and(&a)
    .and(&b)
    .for_each(|out_elt, &a_elt, &b_elt| {
        *out_elt = a_elt + b_elt;
    });

println!("{out}");
```

#### broadcasting
- broadcasts dimensions out of the box
- example: add a 1D row vector to every row of a 2D matrix:

```rust
use ndarray::{Array2, Array1, Zip};

let mut a = Array2::zeros((3, 4));
let row: Array1<f64> = Array1::from(vec![1.0, 2.0, 3.0, 4.0]);

Zip::from(&mut a)
    .and(&row) // row is broadcast along axis 0
    .for_each(|a_elt, &r| {
        *a_elt = r;
    });

println!("{a}");
```


# anki

START
Basic
how does element wise processing of arrays work in [[rust]]
- difference to [[r std]]
- in place update pattern
- broadcasting

Back: 
## ndarray
- library for n dimensional array processing like [[numpy]]

### zip
- used for [[r iterator]] based element wise processing of one or more arrays
- similar to the [[r std]] zip for general [[r iterator]] but with the following differences

`std::iter::zip`
- Works on **any iterators**.
- Doesn’t know about shapes, axes, or broadcasting.
- Doesn’t give cache-friendly access to `ndarray` storage automatically.
`ndarray::Zip`
- Works on **arrays and views** (`ArrayBase`, `ArrayView`, `ArrayViewMut`).
- Understands **dimensions, strides, and broadcasting**.
- Optimizes iteration order for performance.
- Can be extended with parallel iteration via [[r rayon]]


```rust
use ndarray::{Array2, Zip};

let a = Array2::<f64>::zeros((2, 2));
let b = Array2::<f64>::ones((2, 2));

Zip::from(&a)
    .and(&b)
    .for_each(|x, y| {
        println!("{}", x + y);
    });
```

this is equivalent to the following:

```rust
use ndarray::Array2;

let a = Array2::<f64>::zeros((2, 2));
let b = Array2::<f64>::ones((2, 2));

for i in 0..2 {
    for j in 0..2 {
        println!("{}", a[[i, j]] + b[[i, j]]);
    }
}
```

#### in place update pattern

```rust
use ndarray::{Array2, Zip};

let mut out = Array2::<f64>::zeros((2, 2));
let a = Array2::<f64>::from_elem((2, 2), 2.0);
let b = Array2::<f64>::from_elem((2, 2), 3.0);

Zip::from(&mut out)
    .and(&a)
    .and(&b)
    .for_each(|out_elt, &a_elt, &b_elt| {
        *out_elt = a_elt + b_elt;
    });

println!("{out}");
```

#### broadcasting
- broadcasts dimensions out of the box
- example: add a 1D row vector to every row of a 2D matrix:

```rust
use ndarray::{Array2, Array1, Zip};

let mut a = Array2::zeros((3, 4));
let row: Array1<f64> = Array1::from(vec![1.0, 2.0, 3.0, 4.0]);

Zip::from(&mut a)
    .and(&row) // row is broadcast along axis 0
    .for_each(|a_elt, &r| {
        *a_elt = r;
    });

println!("{a}");
```

________________


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
<!--ID: 1763972174687-->
END



START
Basic
2 options for array/matrix based data processing in [[rust]] like [[numpy]]


Back: 

### `ndarray`
- Think: **Rust NumPy**.
- Arbitrary **N-dimensional** arrays: `Array1`, `Array2`, `Array3`, `ArrayD`.
- Good for:
    - Data/ML workloads
    - Numerical computing
    - Image processing, tensors, statistics
    - Interfacing with Python-like stacks

### `nalgebra`
- Think: **Eigen / GLM in Rust**.
- Focused on **linear algebra**: vectors, matrices, transformations.
- Good for:
    - 2D/3D graphics and game dev
    - Robotics, control, kinematics
    - Numerical linear algebra where dimensions matter

## ndarray
- library for n dimensional array processing like [[numpy]]

### zip
- used for [[r iterator]] based element wise processing of one or more arrays
- similar to the [[r std]] zip for general [[r iterator]] but with the following differences

`std::iter::zip`
- Works on **any iterators**.
- Doesn’t know about shapes, axes, or broadcasting.
- Doesn’t give cache-friendly access to `ndarray` storage automatically.
`ndarray::Zip`
- Works on **arrays and views** (`ArrayBase`, `ArrayView`, `ArrayViewMut`).
- Understands **dimensions, strides, and broadcasting**.
- Optimizes iteration order for performance.
- Can be extended with parallel iteration via [[r rayon]]


```rust
use ndarray::{Array2, Zip};

let a = Array2::<f64>::zeros((2, 2));
let b = Array2::<f64>::ones((2, 2));

Zip::from(&a)
    .and(&b)
    .for_each(|x, y| {
        println!("{}", x + y);
    });
```

this is equivalent to the following:

```rust
use ndarray::Array2;

let a = Array2::<f64>::zeros((2, 2));
let b = Array2::<f64>::ones((2, 2));

for i in 0..2 {
    for j in 0..2 {
        println!("{}", a[[i, j]] + b[[i, j]]);
    }
}
```

#### in place update pattern

```rust
use ndarray::{Array2, Zip};

let mut out = Array2::<f64>::zeros((2, 2));
let a = Array2::<f64>::from_elem((2, 2), 2.0);
let b = Array2::<f64>::from_elem((2, 2), 3.0);

Zip::from(&mut out)
    .and(&a)
    .and(&b)
    .for_each(|out_elt, &a_elt, &b_elt| {
        *out_elt = a_elt + b_elt;
    });

println!("{out}");
```

#### broadcasting
- broadcasts dimensions out of the box
- example: add a 1D row vector to every row of a 2D matrix:

```rust
use ndarray::{Array2, Array1, Zip};

let mut a = Array2::zeros((3, 4));
let row: Array1<f64> = Array1::from(vec![1.0, 2.0, 3.0, 4.0]);

Zip::from(&mut a)
    .and(&row) // row is broadcast along axis 0
    .for_each(|a_elt, &r| {
        *a_elt = r;
    });

println!("{a}");
```


Tags: code rust
<!--ID: 1763972174690-->
END
