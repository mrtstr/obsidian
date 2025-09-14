### async
- standard was for defining concurrent workloads in [[rust]] (lazy evaluation)
- turn [[r function]] into `Future` which is not evaluated immediately
- just defines the `Future` but needs an executor like [[r tokio]]
- good for non-blocking IO heavy operations and not for [[li cpu]] heavy calculation's

#### difference to threads
- does not support [[li thread|multithreading]] out of the box → all futures run in the same [[li thread]] but of one waits it returns the executor
- futures are mach more lightweight than threads without a separate [[li stack]]
- even with a thread-pool not optimized for high-throughput CPU-bound parallelism → use [[r thread]] or [[r rayon]] for [[li cpu]] heavy parallelization
#### syntax
- define a [[r function]] as a `Future`

```rust
async fn fetch_data() -> u32 {
    42
}
```

- define a future and execute it

```rust
#[tokio::main] // sets up the async runtime
async fn main() {
    let future = fetch_data(); 
    // define a future
    // calculation not started
    let result = future.await; 
    // start executing and wait until result is ready
    // collect result
    println!("Got: {result}");
}
```

- define two futures and execute them concurrently

```rust
async fn run() {
    let f1 = fetch_data();
    let f2 = fetch_data();

    // Run them concurrently
    let (r1, r2) = future::join(f1, f2).await;
    // let (r1, r2) = tokio::join!(f1, f2); // same with a macro
    let r1 = r1?; 
    // propagate JoinError if task panicked/cancelled
    let r2 = r2?;
    println!("Results: {r1}, {r2}");
}
```

![[r tokio#tokio]]


# anki

START
Basic
[[r async]]
- concept
- difference to multi threading
- example: create two futures and execute them concurrently
Back: 
### async
- standard was for defining concurrent workloads in [[rust]] (lazy evaluation)
- turn [[r function]] into `Future` which is not evaluated immediately
- just defines the `Future` but needs an executor like [[r tokio]]
- good for non-blocking IO heavy operations and not for [[li cpu]] heavy calculation's

#### difference to threads
- does not support [[li thread|multithreading]] out of the box → all futures run in the same [[li thread]] but of one waits it returns the executor
- futures are mach more lightweight than threads without a separate [[li stack]]
- even with a thread-pool not optimized for high-throughput CPU-bound parallelism → use [[r thread]] or [[r rayon]] for [[li cpu]] heavy parallelization
#### syntax
- define a [[r function]] as a `Future`

```rust
async fn fetch_data() -> u32 {
    42
}
```

- define a future and execute it

```rust
#[tokio::main] // sets up the async runtime
async fn main() {
    let future = fetch_data(); 
    // define a future
    // calculation not started
    let result = future.await; 
    // start executing and wait until result is ready
    // collect result
    println!("Got: {result}");
}
```

- define two futures and execute them concurrently

```rust
async fn run() {
    let f1 = fetch_data();
    let f2 = fetch_data();

    // Run them concurrently
    let (r1, r2) = future::join(f1, f2).await;
    // let (r1, r2) = tokio::join!(f1, f2); // same with a macro
    let r1 = r1?; 
    // propagate JoinError if task panicked/cancelled
    let r2 = r2?;
    println!("Results: {r1}, {r2}");
}
```

### tokio
- asynchronous runtime for [[rust]]
- provides executors for [[r async]] futures

Tags: code rust
<!--ID: 1757840833397-->
END