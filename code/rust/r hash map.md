### hash map
- key value store backed by a hash table comparable to a [[py dict]]
- key and value [[r data type]] have to be homogeneous
- the `key` has to implement a [[r trait]] `Hash` and `Eq` to calculate hashes and compare values and the `value` can have any type
- on the [[li stack]] is a [[r smart pointer]] stored that looks like the following
```rust
HashMap {
    ptr    → 0x1000   (heap buffer, buckets)
    len    = 2        (number of stored entries)
    cap    = 8        (number of buckets allocated)
    hasher = RandomState { ... }
}
```

- on the [[li heap]] there is a [[r vec]] of buckets with each bucket containing a `key` and a `value` and the position in the memory can be found by the hash of the `key`

```rust
buckets[0] = None
buckets[1] = Some(("a", 1))
buckets[2] = None
buckets[3] = Some(("b", 2))
buckets[4] = None
buckets[5] = None
buckets[6] = None
buckets[7] = None
```

- the Hash value is mapped into an index (`hash % capacity`) thus values can be selected and inserted in O(1) is the average case
-  the buffer on the [[li heap]] can grow and shrink dynamically managed by the [[r global allocator]]
- can be mutable or immutable but has to be mutable to store values

#### syntax


```rust
use std::collections::HashMap;

fn main() {
    // Create a new HashMap
    let mut scores = HashMap::new();

    // Insert values
    scores.insert("Alice", 10);
    // only inserts if missing
    scores.entry("Bob").or_insert(20); 
    // an entry can be either `Occupied` or `Vacant`
    // and supports methods like 
    // `.or_insert`, `.or_insert_with`, `.and_modify`
    
    // Access values by immutable reference
    if let Some(score) = scores.get("Alice") {
        println!("Alice's score: {}", score);
    }
    // score is wrapped in Some that con contain value or None
    // only of score contains a value the condition is true
    
    // Access values by mutable reference
	if let Some(score) = scores.get_mut("Bob") {
	    *score += 5;
	}
	
    // Iterate
    for (name, score) in &scores {
        println!("{}: {}", name, score);
    }
    
    scores.remove("Bob");
    
    if scores.contains_key("Bob") {
	    println!("Bob is in the map");
	}
}
```

### b tree map
- has similar api, but the data structure under the hood is different so the operations have different costs
- b trees are ordered so they support [[r range]] querys

- `HashMap`
    - Average O(1) lookup, insert, delete.
    - Worst-case O(n) if many hash collisions.
    - Higher memory overhead (buckets).
- `BTreeMap`
    - O(log n) for lookup, insert, delete.
    - Very cache-friendly (fewer pointers, packed nodes).
    - Lower overhead than hash maps.
# anki


START
Basic
[[r hash map]]
- concept
- representation in the [[li stack]] and [[li heap]]
- how do inserts and reads work?

syntax
- create a [[r hash map]]
- insert in a [[r hash map]] (2 with difference)
- access data (2 with difference)
- iterate over data
- check if exists
- remove

Back: 
### hash map
- key value store backed by a hash table comparable to a [[py dict]]
- key and value [[r data type]] have to be homogeneous
- the `key` has to implement a [[r trait]] `Hash` and `Eq` to calculate hashes and compare values and the `value` can have any type
- on the [[li stack]] is a [[r smart pointer]] stored that looks like the following
```rust
HashMap {
    ptr    → 0x1000   (heap buffer, buckets)
    len    = 2        (number of stored entries)
    cap    = 8        (number of buckets allocated)
    hasher = RandomState { ... }
}
```

- on the [[li heap]] there is a [[r vec]] of buckets with each bucket containing a `key` and a `value` and the position in the memory can be found by the hash of the `key`

```rust
buckets[0] = None
buckets[1] = Some(("a", 1))
buckets[2] = None
buckets[3] = Some(("b", 2))
buckets[4] = None
buckets[5] = None
buckets[6] = None
buckets[7] = None
```

- the Hash value is mapped into an index (`hash % capacity`) thus values can be selected and inserted in O(1) is the average case
-  the buffer on the [[li heap]] can grow and shrink dynamically managed by the [[r global allocator]]
- can be mutable or immutable but has to be mutable to store values

#### syntax


```rust
use std::collections::HashMap;

fn main() {
    // Create a new HashMap
    let mut scores = HashMap::new();

    // Insert values
    scores.insert("Alice", 10);
    // only inserts if missing
    scores.entry("Bob").or_insert(20); 
    // an entry can be either `Occupied` or `Vacant`
    // and supports methods like 
    // `.or_insert`, `.or_insert_with`, `.and_modify`
    
    // Access values by immutable reference
    if let Some(score) = scores.get("Alice") {
        println!("Alice's score: {}", score);
    }
    // score is wrapped in Some that con contain value or None
    // only of score contains a value the condition is true
    
    // Access values by mutable reference
	if let Some(score) = scores.get_mut("Bob") {
	    *score += 5;
	}
	
    // Iterate
    for (name, score) in &scores {
        println!("{}: {}", name, score);
    }
    
    scores.remove("Bob");
    
    if scores.contains_key("Bob") {
	    println!("Bob is in the map");
	}
}
```
Tags: code rust
<!--ID: 1756569351834-->
END


START
Basic
[[r hash map]] vs b tree
- api
- performance

Back: 

### b tree map
- has similar api, but the data structure under the hood is different so the operations have different costs
- b trees are ordered so they support [[r range]] querys

- `HashMap`
    - Average O(1) lookup, insert, delete.
    - Worst-case O(n) if many hash collisions.
    - Higher memory overhead (buckets).
- `BTreeMap`
    - O(log n) for lookup, insert, delete.
    - Very cache-friendly (fewer pointers, packed nodes).
    - Lower overhead than hash maps.
### hash map
- key value store backed by a hash table comparable to a [[py dict]]
- key and value [[r data type]] have to be homogeneous
- the `key` has to implement a [[r trait]] `Hash` and `Eq` to calculate hashes and compare values and the `value` can have any type
- on the [[li stack]] is a [[r smart pointer]] stored that looks like the following
```rust
HashMap {
    ptr    → 0x1000   (heap buffer, buckets)
    len    = 2        (number of stored entries)
    cap    = 8        (number of buckets allocated)
    hasher = RandomState { ... }
}
```

- on the [[li heap]] there is a [[r vec]] of buckets with each bucket containing a `key` and a `value` and the position in the memory can be found by the hash of the `key`

```rust
buckets[0] = None
buckets[1] = Some(("a", 1))
buckets[2] = None
buckets[3] = Some(("b", 2))
buckets[4] = None
buckets[5] = None
buckets[6] = None
buckets[7] = None
```

- the Hash value is mapped into an index (`hash % capacity`) thus values can be selected and inserted in O(1) is the average case
-  the buffer on the [[li heap]] can grow and shrink dynamically managed by the [[r global allocator]]
- can be mutable or immutable but has to be mutable to store values

#### syntax


```rust
use std::collections::HashMap;

fn main() {
    // Create a new HashMap
    let mut scores = HashMap::new();

    // Insert values
    scores.insert("Alice", 10);
    // only inserts if missing
    scores.entry("Bob").or_insert(20); 
    // an entry can be either `Occupied` or `Vacant`
    // and supports methods like 
    // `.or_insert`, `.or_insert_with`, `.and_modify`
    
    // Access values by immutable reference
    if let Some(score) = scores.get("Alice") {
        println!("Alice's score: {}", score);
    }
    // score is wrapped in Some that con contain value or None
    // only of score contains a value the condition is true
    
    // Access values by mutable reference
	if let Some(score) = scores.get_mut("Bob") {
	    *score += 5;
	}
	
    // Iterate
    for (name, score) in &scores {
        println!("{}: {}", name, score);
    }
    
    scores.remove("Bob");
    
    if scores.contains_key("Bob") {
	    println!("Bob is in the map");
	}
}
```
Tags: code rust
<!--ID: 1756569351838-->
END


START
Basic
 what happens in the following [[rust]] snippet?
 
```rust
scores.entry("Bob").or_insert(20); 

if let Some(score) = scores.get("Alice") {
	println!("Alice's score: {}", score);
}

if let Some(score) = scores.get_mut("Bob") {
	*score += 5;
}
}
```

Back: 

#### syntax


```rust
use std::collections::HashMap;

fn main() {
    // Create a new HashMap
    let mut scores = HashMap::new();

    // Insert values
    scores.insert("Alice", 10);
    // only inserts if missing
    scores.entry("Bob").or_insert(20); 
    // an entry can be either `Occupied` or `Vacant`
    // and supports methods like 
    // `.or_insert`, `.or_insert_with`, `.and_modify`
    
    // Access values by immutable reference
    if let Some(score) = scores.get("Alice") {
        println!("Alice's score: {}", score);
    }
    // score is wrapped in Some that con contain value or None
    // only of score contains a value the condition is true
    
    // Access values by mutable reference
	if let Some(score) = scores.get_mut("Bob") {
	    *score += 5;
	}
	
    // Iterate
    for (name, score) in &scores {
        println!("{}: {}", name, score);
    }
    
    scores.remove("Bob");
    
    if scores.contains_key("Bob") {
	    println!("Bob is in the map");
	}
}
```

### hash map
- key value store backed by a hash table comparable to a [[py dict]]
- key and value [[r data type]] have to be homogeneous
- the `key` has to implement a [[r trait]] `Hash` and `Eq` to calculate hashes and compare values and the `value` can have any type
- on the [[li stack]] is a [[r smart pointer]] stored that looks like the following
```rust
HashMap {
    ptr    → 0x1000   (heap buffer, buckets)
    len    = 2        (number of stored entries)
    cap    = 8        (number of buckets allocated)
    hasher = RandomState { ... }
}
```

- on the [[li heap]] there is a [[r vec]] of buckets with each bucket containing a `key` and a `value` and the position in the memory can be found by the hash of the `key`

```rust
buckets[0] = None
buckets[1] = Some(("a", 1))
buckets[2] = None
buckets[3] = Some(("b", 2))
buckets[4] = None
buckets[5] = None
buckets[6] = None
buckets[7] = None
```

- the Hash value is mapped into an index (`hash % capacity`) thus values can be selected and inserted in O(1) is the average case
-  the buffer on the [[li heap]] can grow and shrink dynamically managed by the [[r global allocator]]
- can be mutable or immutable but has to be mutable to store values


Tags: code rust
<!--ID: 1756627337946-->
END