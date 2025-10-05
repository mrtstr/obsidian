## linked list example
- the standard implementation of a [[forward linked list]] does not comply to rusts [[r ownership]] rules
- the following implementation is memory safe and ownership compliant
	- each node of the list owns its complete tail
	- the tail is stored on the [[heap]] because the size is not known at compile time

caveats:
- that [[forward linked list]] does not rally play a role in [[rust]] because a [[r vec]] is almost always faster
- the existing implementation in the [[r std]] is using [[r unsafe]] and is implemented differently


```rust
#[derive(Debug, PartialEq)]
enum List {
    Cons(i32, Box<List>), 
    Nil,
}
```

### add a from vec constructor


```rust
impl From<Vec<i32>> for List {
    fn from(vec: Vec<i32>) -> List {
        vec.into_iter() 
            .rev() 
            .fold(List::Nil, |current, val| List::Cons(val, Box::new(current))) 
    }
}

fn main() {
    let li = List::from(vec![1,23,4,5345,67,456,3]);
}
```

### functions for retrieving the data and the tail

```rust
impl List {
    #[inline]
    fn head(&self) -> Option<&i32> {
        match self {
            List::Cons(v, _) => Some(v),
            List::Nil => None,
        }
    }

    #[inline]
    fn tail(&self) -> Option<&List> {
        match self {
            List::Cons(_, next) => Some(next),
            List::Nil => None,
        }
    }

}



fn main() {
    let li = List::from(vec![1,23,4,5345,67,456,3]);
    println!("FIRST NUMBER: {}", li.head().unwrap());
    println!("SECOND NUMBER: {}", li.tail().unwrap().head().unwrap());


}
```

### make the function iteratable


```rust
impl List {
    /// Borrowing iterator
    fn iter(&self) -> Iter<'_> {
        Iter { next: Some(self) }
    }
}

impl From<Vec<i32>> for List {
    fn from(vec: Vec<i32>) -> List {
        vec.into_iter() 
            .rev() 
            .fold(List::Nil, |current, val| List::Cons(val, Box::new(current))) 
    }
}

/// Borrowing iterator over List values
struct Iter<'a> {
    next: Option<&'a List>,
}

impl<'a> Iterator for Iter<'a> {
    type Item = i32;

    fn next(&mut self) -> Option<Self::Item> {
        match self.next.take()? {
            List::Cons(v, next) => {
                self.next = Some(next);
                Some(*v)
            }
            List::Nil => None,
        }
    }
}

fn main() {
    let li = List::from(vec![1,23,4,5345,67,456,3]);
    for (i, val) in li.iter().enumerate() {
        println!("{}th number in list: {}",i,  val);
    }
}
```

![[r iterator#iterator]]


# anki

START
Basic
[[r linked list example]]
- ownership compliant implementation

Back: 
## linked list example
- the standard implementation of a [[forward linked list]] does not comply to rusts [[r ownership]] rules
- the following implementation is memory safe and ownership compliant
	- each node of the list owns its complete tail
	- the tail is stored on the [[heap]] because the size is not known at compile time

caveats:
- that [[forward linked list]] does not rally play a role in [[rust]] because a [[r vec]] is almost always faster
- the existing implementation in the [[r std]] is using [[r unsafe]] and is implemented differently


```rust
#[derive(Debug, PartialEq)]
enum List {
    Cons(i32, Box<List>), 
    Nil,
}
```




Tags: code rust
<!--ID: 1759683035812-->
END


START
Basic
- write a from [[r vec]] constructor for the following [[r linked list example]]
- add functions for retrieving the trail and the value

```rust
#[derive(Debug, PartialEq)]
enum List {
    Cons(i32, Box<List>), 
    Nil,
}
```

Back: 
## linked list example
- the standard implementation of a [[forward linked list]] does not comply to rusts [[r ownership]] rules
- the following implementation is memory safe and ownership compliant
	- each node of the list owns its complete tail
	- the tail is stored on the [[heap]] because the size is not known at compile time

caveats:
- that [[forward linked list]] does not rally play a role in [[rust]] because a [[r vec]] is almost always faster
- the existing implementation in the [[r std]] is using [[r unsafe]] and is implemented differently


```rust
#[derive(Debug, PartialEq)]
enum List {
    Cons(i32, Box<List>), 
    Nil,
}
```

### add a from vec constructor

```rust
impl From<Vec<i32>> for List {
    fn from(vec: Vec<i32>) -> List {
        vec.into_iter() 
            .rev() 
            .fold(List::Nil, |current, val| List::Cons(val, Box::new(current))) 
    }
}

fn main() {
    let li = List::from(vec![1,23,4,5345,67,456,3]);
}
```

### functions for retrieving the data and the tail

```rust
impl List {
    #[inline]
    fn head(&self) -> Option<&i32> {
        match self {
            List::Cons(v, _) => Some(v),
            List::Nil => None,
        }
    }

    #[inline]
    fn tail(&self) -> Option<&List> {
        match self {
            List::Cons(_, next) => Some(next),
            List::Nil => None,
        }
    }

}



fn main() {
    let li = List::from(vec![1,23,4,5345,67,456,3]);
    println!("FIRST NUMBER: {}", li.head().unwrap());
    println!("SECOND NUMBER: {}", li.tail().unwrap().head().unwrap());


}
```



Tags: code rust
<!--ID: 1759683035817-->
END


START
Basic
make the following [[r linked list example]] iteratable by implementing the [[r iterator]] trait


```rust
#[derive(Debug, PartialEq)]
enum List {
    Cons(i32, Box<List>), 
    Nil,
}
```



Back: 
## linked list example
- the standard implementation of a [[forward linked list]] does not comply to rusts [[r ownership]] rules
- the following implementation is memory safe and ownership compliant
	- each node of the list owns its complete tail
	- the tail is stored on the [[heap]] because the size is not known at compile time

caveats:
- that [[forward linked list]] does not rally play a role in [[rust]] because a [[r vec]] is almost always faster
- the existing implementation in the [[r std]] is using [[r unsafe]] and is implemented differently


```rust
#[derive(Debug, PartialEq)]
enum List {
    Cons(i32, Box<List>), 
    Nil,
}
```

### add a from vec constructor

```rust
impl From<Vec<i32>> for List {
    fn from(vec: Vec<i32>) -> List {
        vec.into_iter() 
            .rev() 
            .fold(List::Nil, |current, val| List::Cons(val, Box::new(current))) 
    }
}

fn main() {
    let li = List::from(vec![1,23,4,5345,67,456,3]);
}
```


### make the function iteratable


```rust
impl List {
    /// Borrowing iterator
    fn iter(&self) -> Iter<'_> {
        Iter { next: Some(self) }
    }
}

impl From<Vec<i32>> for List {
    fn from(vec: Vec<i32>) -> List {
        vec.into_iter() 
            .rev() 
            .fold(List::Nil, |current, val| List::Cons(val, Box::new(current))) 
    }
}

/// Borrowing iterator over List values
struct Iter<'a> {
    next: Option<&'a List>,
}

impl<'a> Iterator for Iter<'a> {
    type Item = i32;

    fn next(&mut self) -> Option<Self::Item> {
        match self.next.take()? {
            List::Cons(v, next) => {
                self.next = Some(next);
                Some(*v)
            }
            List::Nil => None,
        }
    }
}

fn main() {
    let li = List::from(vec![1,23,4,5345,67,456,3]);
    for (i, val) in li.iter().enumerate() {
        println!("{}th number in list: {}",i,  val);
    }
}
```

________

### iterator
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


Tags: code rust
<!--ID: 1759683035820-->
END