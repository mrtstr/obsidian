## [[py iterator]] protocol
- is an [[py object]] that has the following two methods impemented
1) `__iter__()`: Usualy called by the [[py buidin functions|buidin function inter()]] to convert a [[py interatable]] into an [[py iterator]]. If the object is already an [[py iterator]] it returns itself.
2) `__next__()`: computes and returns the next value in the squence

## how to create a [[py iterator]]

### can be created by a [[py generator]]

![[py generator#py generator definition]]

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
- is an [[py object]] that has the following two methods impemented
1) `__iter__()`: Usualy called by the [[py buidin functions|buidin function inter()]] to convert a [[py interatable]] into an [[py iterator]]. If the object is already an [[py iterator]] it returns itself.
2) `__next__()`: computes and returns the next value in the squence

## how to create a [[py iterator]]

### can be created by a [[py generator]]

### [[py generator]] definition
- [[py generator|generators]] are a blueprint for creating a [[py iterator]]
- the [[py generator]] defines a sequeny and when `next(myiterator)` is called the next element is returned
- only one element at a time is loaded, and thus it's useful for greater than memory data
- can be defined by a special function with the keywork `yield` or by a class the implements the iterator protocol

### using the [[py buidin functions|buidin function iter]] `iter(iteratable_object)` from a [[py interatable]] [[py object]]

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