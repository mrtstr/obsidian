- Underlying function called by [[sum]]: add.reduce 
- additional features like add.reduceat,

```python
a = np.array([1,2,3,4,5])
print(np.add.reduceat(a, np.array([2,3])))
# np.add.reduce(a[2:3]) np.add.reduce(a[3:])
# [3 9]
print(np.add.reduce(a))
# 15
```

- add number of elements defined in array
- useful when working with [[dimensions with different sizes]]
1) use [[add.accumulate]] to translate number of elements in indices
2) remove the last element and add a 0 at the start
3) use add.reduceat
```python
a = np.array([1,2,3,4,5,6])
b = np.array([2, 2, 2])
# [2 2 2]
b = np.add.accumulate(b)
# [2 4 6]
b = np.insert(
	np.delete(b, -1),
	0, 0
)
# [0 2 4]
print(np.add.reduceat(a, b))
# [ 3 7 11]  1+2 3+4 5+6 
```

START
Basic
add number of elements defined in numpy array
Back: 

1) use [[add.accumulate]] to translate number of elements in indices
2) remove the last element and add a 0 at the start
3) use add.reduceat
```python
a = np.array([1,2,3,4,5,6])
b = np.array([2, 2, 2])
# [2 2 2]
b = np.add.accumulate(b)
# [2 4 6]
b = np.insert(
	np.delete(b, -1),
	0, 0
)
# [0 2 4]
print(np.add.reduceat(a, b))
# [ 3 7 11]  1+2 3+4 5+6 
```
(useful when working with [[dimensions with different sizes]])
Tags: code, numpy
<!--ID: 1662453192724-->
END

START
Basic
behaviour of np.add.reduceat and np.add.reduce
Back: 
reduce
- underlying function of np.sum
- sum over given dimension wich reduces dimension
```python
a = np.array([1,2,3,4,5])
print(np.add.reduce(array = a, axis=0))
# 15
```

reduceat
- sum between indices defined in second array
```python
a = np.array([1,2,3,4,5])
print(np.add.reduceat(array = a, indices = np.array([2,3], axis=0)))
# np.add.reduce(a[2:3]) np.add.reduce(a[3:])
# [3 9]
```
Tags: code, numpy
<!--ID: 1662453192728-->
END