- [[py generator|generators]] are a special kind of [[py function]] that return a [[py lazy iterator]]
- the [[py generator]] defines a sequeny and when `next(myiterator)` is called the next element is returned
- only one element at a time is loaded and thus it's useful for greater than memory data

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
next(iterator_pow_two) # 4
next(iterator_pow_two) # 8
```


# anki

START
Basic
what does a [[py generator]] do?
Back: 
- [[py generator|generators]] are a special kind of [[py function]] that return a [[py lazy iterator]]
- the [[py generator]] defines a sequeny and when `next(myiterator)` is called the next element is returned
- only one element is caluclated at a time

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
next(iterator_pow_two) # 4
next(iterator_pow_two) # 8
```

Tags: code python
<!--ID: 1697993323533-->
END

START
Basic
[[py generator]]
- example define a infinite [[py iterator]] that returns the power of two
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

- [[py generator|generators]] are a special kind of [[py function]] that return a [[py lazy iterator]]
- the [[py generator]] defines a sequeny and when `next(myiterator)` is called the next element is returned
- only one element at a time is loaded and thus it's useful for greater than memory data

Tags: code python
<!--ID: 1697993323538-->
END