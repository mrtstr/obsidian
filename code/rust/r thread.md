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

### inter thread communication
- with channels, [[r thread]] can communicate with reach other
- there can be multiple senders but just one receiver (out of the box)
- when multiple receivers are needed a [[r Mutex (mutual exclusion)]] wrapper can be used
- a channel can be used for all [[r data type]]

```rust
use std::sync::mpsc;
use std::{thread, time};

fn main() {
	let (sender, receiver) = mpsc::channel();
	let sender2 = sender.clone();
	// Spawn a producer thread
	thread::spawn(move || {
		let sleep_mills = time::Duration::from_millis(1);
		
		let val = String::from("h");
		sender.send(val).unwrap();
		thread::sleep(sleep_mills);
		let val = String::from("l");
		sender.send(val).unwrap();
		thread::sleep(sleep_mills);
		let val = String::from("o");
		sender.send(val).unwrap();
	});
	
	thread::spawn(move || {
		let sleep_mills = time::Duration::from_millis(1);
		
		let val = String::from("e");
		sender2.send(val).unwrap();
		thread::sleep(sleep_mills);
		let val = String::from("l");
		sender2.send(val).unwrap();
		thread::sleep(sleep_mills);
	});
	
	for r in receiver.iter() {
		println!("{}", r);
	}
}
```

# -------------

![[r Arc (atomic reference counted)#atomic reference counted]]

![[r Mutex (mutual exclusion)#Mutex (mutual exclusion)]]


![[r RwLock (read–write lock)#RwLock (read–write lock)]]


![[li thread#OS thread]]



# anki

START
Basic
[[r thread]]
- concept
- when to use it and when not
- basic example with explanation: start two parallel running [[r thread|threads]]
- how to move data between threads
	- move ownership
	- no zero copy reference to multiple threads
	- granular read and write access during multi threading
- concept for communication between threads without shared memory

Back: 
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

### inter thread communication
- with channels, [[r thread]] can communicate with reach other
- there can be multiple senders but just one receiver (out of the box)
- when multiple receivers are needed a [[r Mutex (mutual exclusion)]] wrapper can be used
- a channel can be used for all [[r data type]]

```rust
use std::sync::mpsc;
use std::{thread, time};

fn main() {
	let (sender, receiver) = mpsc::channel();
	let sender2 = sender.clone();
	// Spawn a producer thread
	thread::spawn(move || {
		let sleep_mills = time::Duration::from_millis(1);
		
		let val = String::from("h");
		sender.send(val).unwrap();
		thread::sleep(sleep_mills);
		let val = String::from("l");
		sender.send(val).unwrap();
		thread::sleep(sleep_mills);
		let val = String::from("o");
		sender.send(val).unwrap();
	});
	
	thread::spawn(move || {
		let sleep_mills = time::Duration::from_millis(1);
		
		let val = String::from("e");
		sender2.send(val).unwrap();
		thread::sleep(sleep_mills);
		let val = String::from("l");
		sender2.send(val).unwrap();
		thread::sleep(sleep_mills);
	});
	
	for r in receiver.iter() {
		println!("{}", r);
	}
}
```

___________

## [[li thread]]
- flow of execution through the [[li process]] [[li code segment|code]]
- can be [[li scheduling|scheduled]] for execution independently by the [[li kernel]]
- to keep track of their execution flow they have their own
	1.  [[li program counter]] to keep track of which instruction to execute next.
	2.  [[li cpu register]] that holds current working variables
	3.  [[li stack]] and stack pointer withing the [[li process]] [[li virtual memory]] 
- [[li thread|threads]] share their [[li process|processes]] resources like
	- [[li virtual memory]] space 
		- threads have technically access to each others [[li stack|stacks]]
		- [[li heap]]
		- [[li code segment]]
		- [[li data segment]]
	- open [[li file|files]] ([[li standard streams]])



## [[li state|state]] of a [[li thread|thread]] (of a [[li process|process]])
-   `D` = **uninterruptible sleep**: waiting for a resource to be available (will wakeup to handle signals)
-   `R` = **running**: running or it’s ready to run
-   `S` = **sleeping**: waiting for a resource to be available (will not wakeup to handle signals)
-   `T` = **traced or stopped**
-   `Z` = **zombie**: terminated child process that remains in the system's process table while waiting for its parent process to collect its exit status

### [[li thread]] handling threads
-   PID: Unique process identifier
-   LWP (lightweight process): Unique thread identifier inside a process
-   NLWP (number of lightweight process): Number of threads for a given [[li process]]
```sh
ps -efL  # print all threads
```

### [[li thread]] creation
- can be created with the [[li syscall]] [[li clone]] (with additional flags)

#### [[li clone]]
- The [[li clone]] [[li syscall]] is an upgraded version of the [[li fork]] call.
- [[linux]] [[li syscall]] for creating a new [[li process]] from a [[li parent process]] by duplicating the calling [[li parent process]] but gives more precise control over the data shared between the parent and child [[li process|processes]]
- used for creating [[li process]] or [[li thread]]

 flags
- `CLONE_FS`    File-system information is shared
- `CLONE_VM`    The same memory space is shared
- `CLONE_SIGHAND` Signal handlers are shared
- `CLONE_FILES` The set of open files is shared

### removing [[li thread]]
- [[li thread]] can only be removed from the context of the [[li process]] (by another [[li thread]])
- `pthread_kill` function can remove a [[li thread]] when called by another thread if the same [[li process]]

### [[li signal]] Handling
-  threads ca indicate which signals they are accepting and which they are ignoring 
- the signal can only be delivered to one thread, which is generally the first thread that is accepting that particular [[li signal]]

Tags: code rust
<!--ID: 1757864606167-->
END




START
Basic
what is wrong here and how to fix it?

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

Back: 

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

### inter thread communication
- with channels, [[r thread]] can communicate with reach other
- there can be multiple senders but just one receiver (out of the box)
- when multiple receivers are needed a [[r Mutex (mutual exclusion)]] wrapper can be used
- a channel can be used for all [[r data type]]

```rust
use std::sync::mpsc;
use std::{thread, time};

fn main() {
	let (sender, receiver) = mpsc::channel();
	let sender2 = sender.clone();
	// Spawn a producer thread
	thread::spawn(move || {
		let sleep_mills = time::Duration::from_millis(1);
		
		let val = String::from("h");
		sender.send(val).unwrap();
		thread::sleep(sleep_mills);
		let val = String::from("l");
		sender.send(val).unwrap();
		thread::sleep(sleep_mills);
		let val = String::from("o");
		sender.send(val).unwrap();
	});
	
	thread::spawn(move || {
		let sleep_mills = time::Duration::from_millis(1);
		
		let val = String::from("e");
		sender2.send(val).unwrap();
		thread::sleep(sleep_mills);
		let val = String::from("l");
		sender2.send(val).unwrap();
		thread::sleep(sleep_mills);
	});
	
	for r in receiver.iter() {
		println!("{}", r);
	}
}
```

Tags: code rust
<!--ID: 1757864606170-->
END


START
Basic
[[r thread]] example: sum up a [[r vec]] in a separate [[r thread]] and print the result in the main thread

Back: 

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

### inter thread communication
- with channels, [[r thread]] can communicate with reach other
- there can be multiple senders but just one receiver (out of the box)
- when multiple receivers are needed a [[r Mutex (mutual exclusion)]] wrapper can be used
- a channel can be used for all [[r data type]]

```rust
use std::sync::mpsc;
use std::{thread, time};

fn main() {
	let (sender, receiver) = mpsc::channel();
	let sender2 = sender.clone();
	// Spawn a producer thread
	thread::spawn(move || {
		let sleep_mills = time::Duration::from_millis(1);
		
		let val = String::from("h");
		sender.send(val).unwrap();
		thread::sleep(sleep_mills);
		let val = String::from("l");
		sender.send(val).unwrap();
		thread::sleep(sleep_mills);
		let val = String::from("o");
		sender.send(val).unwrap();
	});
	
	thread::spawn(move || {
		let sleep_mills = time::Duration::from_millis(1);
		
		let val = String::from("e");
		sender2.send(val).unwrap();
		thread::sleep(sleep_mills);
		let val = String::from("l");
		sender2.send(val).unwrap();
		thread::sleep(sleep_mills);
	});
	
	for r in receiver.iter() {
		println!("{}", r);
	}
}
```

Tags: code rust
<!--ID: 1757864606172-->
END


START
Basic
inter [[r thread]] communication
- concept
- example: send a combined string from two threads one char at a time and receive them just in time in the main thread

Back: 

### inter thread communication
- with channels, [[r thread]] can communicate with reach other
- there can be multiple senders but just one receiver (out of the box)
- when multiple receivers are needed a [[r Mutex (mutual exclusion)]] wrapper can be used
- a channel can be used for all [[r data type]]

```rust
use std::sync::mpsc;
use std::{thread, time};

fn main() {
	let (sender, receiver) = mpsc::channel();
	let sender2 = sender.clone();
	// Spawn a producer thread
	thread::spawn(move || {
		let sleep_mills = time::Duration::from_millis(1);
		
		let val = String::from("h");
		sender.send(val).unwrap();
		thread::sleep(sleep_mills);
		let val = String::from("l");
		sender.send(val).unwrap();
		thread::sleep(sleep_mills);
		let val = String::from("o");
		sender.send(val).unwrap();
	});
	
	thread::spawn(move || {
		let sleep_mills = time::Duration::from_millis(1);
		
		let val = String::from("e");
		sender2.send(val).unwrap();
		thread::sleep(sleep_mills);
		let val = String::from("l");
		sender2.send(val).unwrap();
		thread::sleep(sleep_mills);
	});
	
	for r in receiver.iter() {
		println!("{}", r);
	}
}
```

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


Tags: code rust
<!--ID: 1758892127947-->
END