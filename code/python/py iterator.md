## [[py iterator]] protocol
is an [[py object]] that has the following two methods impemented
#### `__iter__()`
- Usualy called by the [[py buidin functions|buidin function inter()]] to convert a [[py interatable]] into an [[py iterator]]. If the object is already an [[py iterator]] it returns itself.
#### `__next__()`
computes and returns the next value in the squence

## how to create a [[py iterator]]

### can be created by a [[py generator]]

![[py generator#py generator definition]]

![[py generator#how to define a py generator]]

### using the [[py buidin functions|buidin function iter]] `iter(iteratable_object)` from a [[py interatable]] [[py object]]

```python
my_counter = iter(range(3))
print(next(my_counter)) # 0
print(next(my_counter)) # 1
print(next(my_counter)) # 2
print(next(my_counter)) # StopIteration
```


# anki

START
Basic
 [[py iterator]] 
 - definition
 - how to create/use
Back: 

## [[py iterator]] protocol
is an [[py object]] that has the following two methods impemented
#### `__iter__()`
- Usualy called by the [[py buidin functions|buidin function inter()]] to convert a [[py interatable]] into an [[py iterator]]. If the object is already an [[py iterator]] it returns itself.
#### `__next__()`
computes and returns the next value in the squence

## how to create a [[py iterator]]

### by a [[py generator]]

- [[py generator|generators]] are a blueprint for creating a [[py iterator]]
- the [[py generator]] defines a sequeny and when `next(myiterator)` is called the next element is returned
- only one element at a time is loaded, and thus it's useful for greater than memory data
- can be defined by a special function with the keywork `yield` or by a class the implements the iterator protocol
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


### using the [[py buidin functions|buidin function iter]] `iter(iteratable_object)` from a [[py interatable]] [[py object]] (e.g. [[py container objects]])

```python
my_counter = iter(range(3))
print(next(my_counter)) # 0
print(next(my_counter)) # 1
print(next(my_counter)) # 2
print(next(my_counter)) # StopIteration
```

Tags: code python
<!--ID: 1698565329751-->
END