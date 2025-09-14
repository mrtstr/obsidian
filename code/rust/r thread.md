## thread
- part of the [[r std]] in [[rust]] to manage [[li thread|OS threads]]
- provides low level API for simple multi threading working flows
- for more complex workflows use [[r rayon]]

### data access and ownership
- [[r ownership]] rules apply across threads
### syntax
- `spawn` starts and new thread (that runs immediately) and returns a **`JoinHandle`** 
- when the join function of the `JoinHandle` is called

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
# -------------

![[li thread#OS thread]]