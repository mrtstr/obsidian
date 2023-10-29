## [[py interatable]] protocol
#### `__iter__()`
- usually called by the [[py buidin functions|buidin function inter()]] to convert a [[py interatable]] into an [[py iterator]]. 

# anki

START
Basic
difference [[py generator]], [[py iterator]], [[py interatable]]
Back: 

### [[py interatable]] protocol
 is an [[py object]] that can be transformed to an [[py iterator]] with the [[py magic method]]  `__iter__()` which is usualy called by the [[py buidin functions|buidin function inter()]] to convert a [[py interatable]] into an [[py iterator]]. 

### [[py generator]] definition
- [[py generator|generators]] are a blueprint for creating a [[py iterator]]
- the [[py generator]] defines a sequeny and when `next(myiterator)` is called the next element is returned
- only one element at a time is loaded, and thus it's useful for greater than memory data
- can be defined by a special function with the keywork `yield` or by a class the implements the iterator protocol

#### [[py iterator]] protocol
- is an [[py object]] that has the following two methods impemented
1) `__iter__()`: Usualy called by the [[py buidin functions|buidin function inter()]] to convert a [[py interatable]] into an [[py iterator]]. If the object is already an [[py iterator]] it returns itself.
2) `__next__()`: computes and returns the next value in the squence

Tags: code python
<!--ID: 1698565329756-->
END