### rayon
- [[r crate]] for running [[r iterator]] in parallel using multiple [[r thread]]
	→ Take my iterator chain and make it run on all CPU cores safely and efficiently
- works with a global [[r thread]] pool that is managed by [[r rayon]]
- in contrast to [[r thread]] of the [[r std]] in [[r rayon]] the threads are nor managed manually, only tasks are created and the tasks which are distributed among the workers in the thread pool of [[r rayon]]

#### rayon iterator api
when using `use rayon::prelude::*;` the following [[r trait]] are implemented for [[r std]] collections types like [[r vec]]
- `IntoParallelRefIterator` which defines `.par_iter()`
- `IntoParallelRefMutIterator` which defines `.par_iter_mut()`
- `IntoParallelIterator` which defines `.into_par_iter()`

- for example squaring numbers and summing them up in parallel

```rust
use rayon::prelude::*;

fn main() {
    let nums: Vec<i32> = (1..=10_000).collect();

    // Sequential
    let sum_seq: i32 = nums.iter().map(|x| x * 2).sum();

    // Parallel
    let sum_par: i32 = nums.par_iter().map(|x| x * 2).sum();

    println!("seq = {}, par = {}", sum_seq, sum_par);
}
```


1) `.par_iter()` splits `nums` into chunks.
2) Each worker thread computes a **thread-local partial sum** after your `map(|x| x * 2)`.
3) Rayon **reduces** those partial sums in a tree (combine pairs, then pairs of pairs, …). Parts of this reduction can run on workers **and/or** the caller thread (Rayon’s `install` lets the caller help).
4) Once the reduction finishes, `.sum()` returns the result to the caller. There’s no “result living in a worker thread”—it’s a plain return value.

#### rayon join api
- with the join api **two** [[r rayon]] **independent** tasks are created that can be executed in parallel with a join in the end (wait until all are finished)
- note: there are not necessity multiple threads created (like this [[r thread]]) for example with a thread pool of one they are till executed sequentially

```rust
use rayon::join;

fn main() {
    let (a, b) = join(
        || (1..=1_000).sum::<i32>(),
        || (1..=1_000).map(|x| x * 2).sum::<i32>(),
    );
    println!("{a}, {b}");
}
```


#### rayon scope api
- with the scope api multiple [[r rayon]] tasks are created that can be executed in parallel on the threads of the thread pool
- the scope is only closed when all tasks are finished → more freedom than with join

```rust
use rayon::scope;

fn main() {
    let mut a = 0;
    let mut b = 0;

    scope(|s| {
        s.spawn(|_| a = (1..=100).sum());
        s.spawn(|_| b = (1..=100).map(|x| x * 2).sum());
    });

    println!("{a}, {b}");
}
```

##### join vs scope
- **`rayon::join`** → best for **exactly two** independent computations, often in **divide-and-conquer** recursion; returns their **results** directly; **lowest overhead**.
- **`rayon::scope`** → best for **N tasks (dynamic or >2)** that may borrow locals; you **spawn** tasks into the pool and wait for all before the scope ends; no direct return values (write into captured vars or channels).

#### polars paritioned df example

```rust
use eyre::{Result, WrapErr};
use polars::prelude::*;
use rayon::prelude::*;

fn per_partition(df: DataFrame) -> Result<DataFrame> {
    // add context that shows *which* step failed inside this worker
    let out = df.lazy()
        .groupby([col("key")])
        .agg([
            col("value").mean().alias("value_mean"),
            col("value").sum().alias("value_sum"),
        ])
        .collect()
        .wrap_err("polars groupby/collect failed in per_partition")?;
    Ok(out)
}

fn main() -> Result<()> {
    // pretty error reports (optional)
    color_eyre::install()?;

    let big_df = LazyFrame::scan_parquet("data/all.parquet", ScanArgsParquet::default())
        .wrap_err("scan_parquet failed")?
        .collect()
        .wrap_err("collect after scan_parquet failed")?;

    let parts = big_df
        .partition_by(["key"], true)
        .wrap_err("partition_by(key) failed")?;

    // If any partition errors, we short-circuit with the first error
    let processed: Vec<DataFrame> = parts
        .into_par_iter()
        .map(|part| per_partition(part))
        .collect::<Result<_>>()?;

    let result = polars::functions::concat_df(&processed)
        .wrap_err("concat_df failed")?;
    println!("{result}");
    Ok(())
}
```


# anki

START
Basic
[[r rayon]]
- concept
- difference to [[r std]] [[r thread]]
- 3 APIs and when to use them
Back: 
### rayon
- [[r crate]] for running [[r iterator]] in parallel using multiple [[r thread]]
	→ Take my iterator chain and make it run on all CPU cores safely and efficiently
- works with a global [[r thread]] pool that is managed by [[r rayon]]
- in contrast to [[r thread]] of the [[r std]] in [[r rayon]] the threads are nor managed manually, only tasks are created and the tasks which are distributed among the workers in the thread pool of [[r rayon]]

#### rayon iterator api
when using `use rayon::prelude::*;` the following [[r trait]] are implemented for [[r std]] collections types like [[r vec]]
- `IntoParallelRefIterator` which defines `.par_iter()`
- `IntoParallelRefMutIterator` which defines `.par_iter_mut()`
- `IntoParallelIterator` which defines `.into_par_iter()`

- for example squaring numbers and summing them up in parallel

```rust
use rayon::prelude::*;

fn main() {
    let nums: Vec<i32> = (1..=10_000).collect();

    // Sequential
    let sum_seq: i32 = nums.iter().map(|x| x * 2).sum();

    // Parallel
    let sum_par: i32 = nums.par_iter().map(|x| x * 2).sum();

    println!("seq = {}, par = {}", sum_seq, sum_par);
}
```


1) `.par_iter()` splits `nums` into chunks.
2) Each worker thread computes a **thread-local partial sum** after your `map(|x| x * 2)`.
3) Rayon **reduces** those partial sums in a tree (combine pairs, then pairs of pairs, …). Parts of this reduction can run on workers **and/or** the caller thread (Rayon’s `install` lets the caller help).
4) Once the reduction finishes, `.sum()` returns the result to the caller. There’s no “result living in a worker thread”—it’s a plain return value.

#### rayon join api
- with the join api **two** [[r rayon]] **independent** tasks are created that can be executed in parallel with a join in the end (wait until all are finished)
- note: there are not necessity multiple threads created (like this [[r thread]]) for example with a thread pool of one they are till executed sequentially

```rust
use rayon::join;

fn main() {
    let (a, b) = join(
        || (1..=1_000).sum::<i32>(),
        || (1..=1_000).map(|x| x * 2).sum::<i32>(),
    );
    println!("{a}, {b}");
}
```


#### rayon scope api
- with the scope api multiple [[r rayon]] tasks are created that can be executed in parallel on the threads of the thread pool
- the scope is only closed when all tasks are finished → more freedom than with join

```rust
use rayon::scope;

fn main() {
    let mut a = 0;
    let mut b = 0;

    scope(|s| {
        s.spawn(|_| a = (1..=100).sum());
        s.spawn(|_| b = (1..=100).map(|x| x * 2).sum());
    });

    println!("{a}, {b}");
}
```

##### join vs scope
- **`rayon::join`** → best for **exactly two** independent computations, often in **divide-and-conquer** recursion; returns their **results** directly; **lowest overhead**.
- **`rayon::scope`** → best for **N tasks (dynamic or >2)** that may borrow locals; you **spawn** tasks into the pool and wait for all before the scope ends; no direct return values (write into captured vars or channels).
_________________

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
Tags: code rust
<!--ID: 1758892127951-->
END



START
Basic
[[r rayon]]
- example: square all numbers from 1 to 10000 and sum them up sequentially and in parallel
- what happens under the hood in the parallel case?
Back: 

#### rayon iterator api
when using `use rayon::prelude::*;` the following [[r trait]] are implemented for [[r std]] collections types like [[r vec]]
- `IntoParallelRefIterator` which defines `.par_iter()`
- `IntoParallelRefMutIterator` which defines `.par_iter_mut()`
- `IntoParallelIterator` which defines `.into_par_iter()`

- for example squaring numbers and summing them up in parallel

```rust
use rayon::prelude::*;

fn main() {
    let nums: Vec<i32> = (1..=10_000).collect();

    // Sequential
    let sum_seq: i32 = nums.iter().map(|x| x * 2).sum();

    // Parallel
    let sum_par: i32 = nums.par_iter().map(|x| x * 2).sum();

    println!("seq = {}, par = {}", sum_seq, sum_par);
}
```


1) `.par_iter()` splits `nums` into chunks.
2) Each worker thread computes a **thread-local partial sum** after your `map(|x| x * 2)`.
3) Rayon **reduces** those partial sums in a tree (combine pairs, then pairs of pairs, …). Parts of this reduction can run on workers **and/or** the caller thread (Rayon’s `install` lets the caller help).
4) Once the reduction finishes, `.sum()` returns the result to the caller. There’s no “result living in a worker thread”—it’s a plain return value.

___________________
### rayon
- [[r crate]] for running [[r iterator]] in parallel using multiple [[r thread]]
	→ Take my iterator chain and make it run on all CPU cores safely and efficiently
- works with a global [[r thread]] pool that is managed by [[r rayon]]
- in contrast to [[r thread]] of the [[r std]] in [[r rayon]] the threads are nor managed manually, only tasks are created and the tasks which are distributed among the workers in the thread pool of [[r rayon]]

#### rayon iterator api
when using `use rayon::prelude::*;` the following [[r trait]] are implemented for [[r std]] collections types like [[r vec]]
- `IntoParallelRefIterator` which defines `.par_iter()`
- `IntoParallelRefMutIterator` which defines `.par_iter_mut()`
- `IntoParallelIterator` which defines `.into_par_iter()`

- for example squaring numbers and summing them up in parallel

```rust
use rayon::prelude::*;

fn main() {
    let nums: Vec<i32> = (1..=10_000).collect();

    // Sequential
    let sum_seq: i32 = nums.iter().map(|x| x * 2).sum();

    // Parallel
    let sum_par: i32 = nums.par_iter().map(|x| x * 2).sum();

    println!("seq = {}, par = {}", sum_seq, sum_par);
}
```


1) `.par_iter()` splits `nums` into chunks.
2) Each worker thread computes a **thread-local partial sum** after your `map(|x| x * 2)`.
3) Rayon **reduces** those partial sums in a tree (combine pairs, then pairs of pairs, …). Parts of this reduction can run on workers **and/or** the caller thread (Rayon’s `install` lets the caller help).
4) Once the reduction finishes, `.sum()` returns the result to the caller. There’s no “result living in a worker thread”—it’s a plain return value.

#### rayon join api
- with the join api **two** [[r rayon]] **independent** tasks are created that can be executed in parallel with a join in the end (wait until all are finished)
- note: there are not necessity multiple threads created (like this [[r thread]]) for example with a thread pool of one they are till executed sequentially

```rust
use rayon::join;

fn main() {
    let (a, b) = join(
        || (1..=1_000).sum::<i32>(),
        || (1..=1_000).map(|x| x * 2).sum::<i32>(),
    );
    println!("{a}, {b}");
}
```


#### rayon scope api
- with the scope api multiple [[r rayon]] tasks are created that can be executed in parallel on the threads of the thread pool
- the scope is only closed when all tasks are finished → more freedom than with join

```rust
use rayon::scope;

fn main() {
    let mut a = 0;
    let mut b = 0;

    scope(|s| {
        s.spawn(|_| a = (1..=100).sum());
        s.spawn(|_| b = (1..=100).map(|x| x * 2).sum());
    });

    println!("{a}, {b}");
}
```

##### join vs scope
- **`rayon::join`** → best for **exactly two** independent computations, often in **divide-and-conquer** recursion; returns their **results** directly; **lowest overhead**.
- **`rayon::scope`** → best for **N tasks (dynamic or >2)** that may borrow locals; you **spawn** tasks into the pool and wait for all before the scope ends; no direct return values (write into captured vars or channels).
_________________

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
Tags: code rust
<!--ID: 1758892127953-->
END



START
Basic
[[r rayon]]
- example use to different APIs for summing up the numbers from 1 to 1000 and the squared numbers from 1 to 1000 in two parallel threads
- what are the differences the `std::threads`?
- compare the two APIs
Back: 

#### rayon join api
- with the join api **two** [[r rayon]] **independent** tasks are created that can be executed in parallel with a join in the end (wait until all are finished)
- note: there are not necessity multiple threads created (like this [[r thread]]) for example with a thread pool of one they are till executed sequentially

```rust
use rayon::join;

fn main() {
    let (a, b) = join(
        || (1..=1_000).sum::<i32>(),
        || (1..=1_000).map(|x| x * 2).sum::<i32>(),
    );
    println!("{a}, {b}");
}
```


#### rayon scope api
- with the scope api multiple [[r rayon]] tasks are created that can be executed in parallel on the threads of the thread pool
- the scope is only closed when all tasks are finished → more freedom than with join

```rust
use rayon::scope;

fn main() {
    let mut a = 0;
    let mut b = 0;

    scope(|s| {
        s.spawn(|_| a = (1..=100).sum());
        s.spawn(|_| b = (1..=100).map(|x| x * 2).sum());
    });

    println!("{a}, {b}");
}
```

##### join vs scope
- **`rayon::join`** → best for **exactly two** independent computations, often in **divide-and-conquer** recursion; returns their **results** directly; **lowest overhead**.
- **`rayon::scope`** → best for **N tasks (dynamic or >2)** that may borrow locals; you **spawn** tasks into the pool and wait for all before the scope ends; no direct return values (write into captured vars or channels).


___________________
### rayon
- [[r crate]] for running [[r iterator]] in parallel using multiple [[r thread]]
	→ Take my iterator chain and make it run on all CPU cores safely and efficiently
- works with a global [[r thread]] pool that is managed by [[r rayon]]
- in contrast to [[r thread]] of the [[r std]] in [[r rayon]] the threads are nor managed manually, only tasks are created and the tasks which are distributed among the workers in the thread pool of [[r rayon]]

#### rayon iterator api
when using `use rayon::prelude::*;` the following [[r trait]] are implemented for [[r std]] collections types like [[r vec]]
- `IntoParallelRefIterator` which defines `.par_iter()`
- `IntoParallelRefMutIterator` which defines `.par_iter_mut()`
- `IntoParallelIterator` which defines `.into_par_iter()`

- for example squaring numbers and summing them up in parallel

```rust
use rayon::prelude::*;

fn main() {
    let nums: Vec<i32> = (1..=10_000).collect();

    // Sequential
    let sum_seq: i32 = nums.iter().map(|x| x * 2).sum();

    // Parallel
    let sum_par: i32 = nums.par_iter().map(|x| x * 2).sum();

    println!("seq = {}, par = {}", sum_seq, sum_par);
}
```


1) `.par_iter()` splits `nums` into chunks.
2) Each worker thread computes a **thread-local partial sum** after your `map(|x| x * 2)`.
3) Rayon **reduces** those partial sums in a tree (combine pairs, then pairs of pairs, …). Parts of this reduction can run on workers **and/or** the caller thread (Rayon’s `install` lets the caller help).
4) Once the reduction finishes, `.sum()` returns the result to the caller. There’s no “result living in a worker thread”—it’s a plain return value.

#### rayon join api
- with the join api **two** [[r rayon]] **independent** tasks are created that can be executed in parallel with a join in the end (wait until all are finished)
- note: there are not necessity multiple threads created (like this [[r thread]]) for example with a thread pool of one they are till executed sequentially

```rust
use rayon::join;

fn main() {
    let (a, b) = join(
        || (1..=1_000).sum::<i32>(),
        || (1..=1_000).map(|x| x * 2).sum::<i32>(),
    );
    println!("{a}, {b}");
}
```


#### rayon scope api
- with the scope api multiple [[r rayon]] tasks are created that can be executed in parallel on the threads of the thread pool
- the scope is only closed when all tasks are finished → more freedom than with join

```rust
use rayon::scope;

fn main() {
    let mut a = 0;
    let mut b = 0;

    scope(|s| {
        s.spawn(|_| a = (1..=100).sum());
        s.spawn(|_| b = (1..=100).map(|x| x * 2).sum());
    });

    println!("{a}, {b}");
}
```

##### join vs scope
- **`rayon::join`** → best for **exactly two** independent computations, often in **divide-and-conquer** recursion; returns their **results** directly; **lowest overhead**.
- **`rayon::scope`** → best for **N tasks (dynamic or >2)** that may borrow locals; you **spawn** tasks into the pool and wait for all before the scope ends; no direct return values (write into captured vars or channels).


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
Tags: code rust
<!--ID: 1758892127956-->
END