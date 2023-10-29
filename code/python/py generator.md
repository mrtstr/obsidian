## [[py generator]] definition
- [[py generator|generators]] are a blueprint for creating a [[py iterator]]
- the [[py generator]] defines a sequeny and when `next(myiterator)` is called the next element is returned
- only one element at a time is loaded, and thus it's useful for greater than memory data
- can be defined by a special function with the keywork `yield` or by a class the implements the iterator protocol

## protocol
![[py iterator#py iterator protocol]]

## how to define a [[py generator]]

### Using the `yield` keyword
```python
def three_count():
	yield 1
	yield 2
	yield 3
iterator_three_count = three_count()
next(iterator_three_count) # 1
next(iterator_three_count) # 2
next(iterator_three_count) # 3
next(iterator_three_count) # error
```

```python
def pow_two():
	num = 1
	while True:
		yield num
		num = num*2
iterator_pow_two = pow_two()
next(iterator_pow_two) # 1
next(iterator_pow_two) # 2
```

### clustome class that implements the [[py iterator]] protocol

```python
class Squares:
    def __init__(self, length):
        self.length = length
        self.current = 0

    def __iter__(self):
        return self

    def __next__(self):
        if self.current >= self.length:
            raise StopIteration
        self.current += 1
        return self.current ** 2
```

# anki

START
Basic
 [[py generator]] 
 - definition
 - how to create/use
Back: 
### [[py generator]] definition
- [[py generator|generators]] are a blueprint for creating a [[py iterator]]
- the [[py generator]] defines a sequeny and when `next(myiterator)` is called the next element is returned
- only one element at a time is loaded, and thus it's useful for greater than memory data
- can be defined by a special function with the keywork `yield` or by a class the implements the iterator protocol

#### [[py iterator]] protocol
- is an [[py object]] that has the following two methods impemented
1) `__iter__()`: Usualy called by the [[py buidin functions|buidin function inter()]] to convert a [[py interatable]] into an [[py iterator]]. If the object is already an [[py iterator]] it returns itself.
2) `__next__()`: computes and returns the next value in the squence

### how to define a [[py generator]]

#### Using the `yield` keyword
```python
def three_count():
	yield 1
	yield 2
	yield 3
iterator_three_count = three_count()
next(iterator_three_count) # 1
next(iterator_three_count) # 2
next(iterator_three_count) # 3
next(iterator_three_count) # error
```

```python
def pow_two():
	num = 1
	while True:
		yield num
		num = num*2
iterator_pow_two = pow_two()
next(iterator_pow_two) # 1
next(iterator_pow_two) # 2
```

#### clustome class that implements the [[py iterator]] protocol

```python
class Squares:
    def __init__(self, length):
        self.length = length
        self.current = 0

    def __iter__(self):
        return self

    def __next__(self):
        if self.current >= self.length:
            raise StopIteration
        self.current += 1
        return self.current ** 2
```

Tags: code python
<!--ID: 1697993323533-->
END

START
Basic
[[py generator]]
- example define a infinite [[py iterator]] that returns the power of two (two methods)
Back: 

```python
def pow_two():
	num = 1
	while True:
		yield num
		num = num*2
iterator_pow_two = pow_two()
next(iterator_pow_two) # 1
next(iterator_pow_two) # 2
next(iterator_pow_two) # 4
next(iterator_pow_two) # 8
```


```python
class pow_two:
    def __init__(self, length):
        self.num = 1

    def __iter__(self):
        return self

    def __next__(self):
        self.current = self.current ** 2
        return self.current
```


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
<!--ID: 1697993323538-->
END