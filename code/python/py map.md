[[py map]] applys a [[py callable object]] to each element in an [[py interatable]]

```python
map(
	function = lambda x: x**2, 
	iterable=[1, 2, 3, 4]
)
# [1, 4, 9, 12]
```


# anki
START
Basic
apply a [[py callable object]] to all elements in an [[py iterator]]
- two methods
Back: 

1) [[py map]] applys a [[py callable object]] to each element in an [[py interatable]]

```python
map(
	function = lambda x: x**2, 
	iterable=[1, 2, 3, 4]
)
# [1, 4, 9, 12]
```
2) [[py list comprehension]]

```python
my_func = lambda x: x**2
mylist = [1, 2, 3, 4]
[
	myfunc(element) 
	for element in mylist
]

# [1, 4, 9, 12]
```
Tags: code python
<!--ID: 1697991973885-->
END