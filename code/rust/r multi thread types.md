## multi thread types
- the following [[r smart pointer]] allow for memory safe working with multiple [[r thread|threads]] on the same data with reads and writes 

locks
- [[r Mutex (mutual exclusion)]] → only one can work can the data at the same time
- [[r RwLock (read–write lock)]] → one writer or multiple readers
- [[r atomics]] → no proper lock but endure [[r atomic operation]] when incrementing counters

managing ownership
- [[r Arc (atomic reference counted)]]: multiple owners → prevent that the data is removed because the owner thread terminates ready



![[r Arc (atomic reference counted)#atomic reference counted]]

![[r Mutex (mutual exclusion)#Mutex (mutual exclusion)]]



![[r RwLock (read–write lock)#RwLock (read–write lock)]]

![[r atomics#atomics]]


![[r smart pointer#smart pointer]]

# anki

START
Basic
[[r multi thread types]]
- 4 [[r smart pointer]] for working with mutual data with multiple [[r thread]]

Back: 
## multi thread types
- the following [[r smart pointer]] allow for memory safe working with multiple [[r thread|threads]] on the same data with reads and writes 

locks
- [[r Mutex (mutual exclusion)]] → only one can work can the data at the same time
- [[r RwLock (read–write lock)]] → one writer or multiple readers
- [[r atomics]] → no proper lock but endure [[r atomic operation]] when incrementing counters

managing ownership
- [[r Arc (atomic reference counted)]]: multiple owners → prevent that the data is removed because the owner thread terminates ready

##### atomic reference counted
- [[r smart pointer]] with non standard [[r ownership]] rules
- [[r smart pointer]] on the [[li stack]] and data on the [[li heap]] 
- Multiple [[r ownership|owners]], single-[[li thread]] or multiple-[[li thread]] of [[r atomic operation]]

```rust
use std::rc::Rc;
let a = Rc::new(42);
let b = Rc::clone(&a);

use std::sync::Arc;
let a = Arc::new(42);
let b = Arc::clone(&a);

```

```
Stack:                   Heap:
+---+      +---+         +--------------+
| a |----->|   |         | Rc box:      |
+---+      +---+         | refcount=2   |
                         | value = 42   |
+---+                    +--------------+
| b |--------------------^
+---+

```

- Both `a` and `b` point to the same heap box.
- Refcount = 2. When last `Rc` is dropped, memory is freed.

##### Mutex (mutual exclusion)
- wraps a value and ensures only one [[r thread]] can access it at once (see [[r multi thread types]])
- when `.lock()` is called a `guard` is returned and as long as that `guard` exists no other thread can get the lock

- in the first example to `guard` is dropped because its scope is closed and in the second example the `guard` is explicitly dropped

```rust
fn main() {
	let counter = Arc::new(Mutex::new(0));
	
	let counter_a = Arc::clone(&counter);
	let counter_b = Arc::clone(&counter);
	
	let h1 = thread::spawn(move || {
		{
			let mut guard = counter_a.lock().unwrap();
			*guard += 1;
			// guard dropped here at end of scope -> unlock
		}
	});
	
	let h2 = thread::spawn(move || {
		let mut guard = counter_b.lock().unwrap();
		*guard += 1;
		drop(guard); // drop guard explicitly
	});
	
	h1.join().unwrap();
	h2.join().unwrap();
	println!("{}", counter.lock().unwrap());
}
```


##### RwLock (read–write lock)
- [[r smart pointer]] that can wrap another [[r data type]] and allow locking it
- allows multiple concurrent reader or one writer
- see [[r multi thread types]]
- has a `read` and `write` functions which return a guard, but only one write `guard` can exist and when a write `guard` exists no read `guard` can exist

```rust
use std::sync::{Arc, RwLock};
use std::thread;

fn main() {
    let data = Arc::new(RwLock::new(vec![1, 2, 3]));

    let readers: Vec<_> = (0..3).map(|_| {
        let data = Arc::clone(&data);
        thread::spawn(move || {
            let guard = data.read().unwrap(); 
            // multiple readers allowed
            println!("len = {}", guard.len());
        })
    }).collect();

    let writer = {
        let data = Arc::clone(&data);
        thread::spawn(move || {
            let mut guard = data.write().unwrap(); 
            // blocks until readers are done
            guard.push(4);
        })
    };

    for r in readers { r.join().unwrap(); }
    writer.join().unwrap();
}
```

### atomics
- more lightweight and low level than [[r RwLock (read–write lock)]] and [[r Mutex (mutual exclusion)]]
- only for simple data structures like bools or int and ensures [[r atomic operation]] when incrementing for example
- used for implementing [[r Arc (atomic reference counted)]]
- for more complex cases use  [[r RwLock (read–write lock)]] and [[r Mutex (mutual exclusion)]]

___________
## thread
- part of the [[r std]] in [[rust]] to manage [[li thread|OS threads]]
- provides low level API for simple multi threading working flows
- for more complex workflows use [[r rayon]]
- for asynchronous IO heavy situations use [[r async]]
### basic usage
- `spawn` starts and new thread (that runs immediately) and returns a **`JoinHandle`** 
- when the join function of the `JoinHandle` is called, the main thread waits until the thread is done and collects its return value

- simple example for running multiple parallel threads:

```rust
use std::thread;

fn main() {
    let handle_a = thread::spawn(|| {
        for i in 1..1000 {
            println!("Hello from spawned thread A {i}");
        }
    });

    let handle_b = thread::spawn(|| {
        for i in 1..1000 {
            println!("Hello from spawned thread B {i}");
        }
    });

    for i in 1..1000 {
        println!("Hello from main thread {i}");
    }

    // Wait for both spawned threads to finish
    handle_a.join().unwrap();
    handle_b.join().unwrap();
}
```
### data access and ownership
- [[r ownership]] rules apply across threads
- it's possible to share read-only access among threads or move ownership

#### move ownership
- with the keyword `move` all the [[r ownership]] to all data that is accessed inside the thread is moved to the thread

```rust
use std::thread;

fn main() {
    let data = vec![1, 2, 3];
    let handle = thread::spawn(move || { 
    // move transfers ownership
        // data is now owned by this thread
        data.iter().sum::<i32>()
    });

    let sum = handle.join().unwrap();
    println!("sum = {sum}");
}
```

#### borrowing data without cloning
- out of the box borrowing to threads works only for status data because otherwise it's not ensured that the main thread lives long enough until the spawned threads terminate its unsafe

- the following does not work because the main [[r thread]] could go out of scope while the treads are still running to the borrows is unsafe

```rust
use std::thread;

fn main() {
	let mut arr = [0; 10];
	let handle_a = thread::spawn(|| {
		let x = &arr[0];
		println!("first = {x}");
	});
	let handle_b = thread::spawn(|| {
		println!("second = {}", &arr[0]);
	});
	handle_a.join().unwrap();
	handle_b.join().unwrap();
}
```

- with scope, it's ensured that the main thread is running long enough until the treads are finished 

```rust
use std::thread;

fn main() {
    let mut arr = [0; 10];

    thread::scope(|s| {
        // Each spawned thread may borrow from arr safely
        s.spawn(|| {
            // immutable borrow
            let x = &arr[0];
            println!("first = {x}");
        });

        s.spawn(|| { 
	        println!("second = {}", &arr[0]); 
        });
    }); 
    // All scoped threads are joined here; 
    // borrows can't outlive arr
}
```

#### read write operations
- use [[r Arc (atomic reference counted)]] and locks like [[r Mutex (mutual exclusion)]] and [[r RwLock (read–write lock)]]

___________

## smart pointer
- [[r struct]] that contains the [[r pointer#raw pointer]] plus metadata like the length and additional behavior for memory management like [[r drop]]
- takes [[r ownership]] of its data
- can have additional logic for releasing the data ([[r drop]]) or borrowing [[r deref]]

- example how the [[r struct]] looks like for a `Vec` [[r smart pointer]] (with `T` the [[r generic type]])

```rust
pub struct Vec<T> {
    ptr: *mut T,   // raw pointer to heap buffer
    len: usize,    // number of elements actually in use
    cap: usize,    // number of elements allocated
}
impl<T> Drop for Vec<T> {
    fn drop(&mut self) {
        // 1. Drop all elements (run their destructors)
        // 2. Free the heap buffer
    }
}
```


- example: allocation of a string: the fields of the [[r struct]] for `ptr` and so on are [[r encapsulation|private]] but can be accessed with a getter method

```rust
let mut s = String::from("hello");
s.as_ptr()   // raw pointer to the memory adress (raw pointer)
s.len()   // number saved bytes
s.capacity() // number of allocated bytes
```

### types of smart pointers
- **`Box<T>`** → one owner, heap storage.
- **`Rc<T>`** → many owners, single-thread, refcount.
- **`Arc<T>`** → many owners, multi-thread, atomic refcount.
- **`RefCell<T>`** → one owner, runtime borrow rules (panics if violated).
- **`Mutex<T>`** → one writer at a time across threads.
- **`RwLock<T>`** → many readers or one writer across threads.

| Smart Pointer | Ownership         | Thread-safe? | Mutability check | Common use case                       |
| ------------- | ----------------- | ------------ | ---------------- | ------------------------------------- |
| `Box<T>`      | Single owner      | N/A          | Compile-time     | Heap storage, recursion               |
| `Rc<T>`       | Shared (refcount) | ❌            | Compile-time     | Shared immutable data (single-thread) |
| `Arc<T>`      | Shared (refcount) | ✅            | Compile-time     | Shared immutable data (multi-thread)  |
| `RefCell<T>`  | Single owner      | ❌            | Runtime          | Interior mutability (single-thread)   |
| `Mutex<T>`    | Shared (lock)     | ✅            | Runtime (lock)   | Shared mutable data (multi-thread)    |
| `RwLock<T>`   | Shared (lock)     | ✅            | Runtime (lock)   | Many readers or one writer            |



Tags: code rust
<!--ID: 1757864606165-->
END