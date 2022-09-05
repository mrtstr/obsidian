- Underlying function called by [[sum]]: add.reduce 
- additional features like add.reduceat, add. accumulate

```python
a = np.array([1,2,3,4,5])
print(np.add.reduceat(a, np.array([2,3])))
# [3 9]
print(np.add.accumulate(a))
# [ 1 3 6 10 15]
print(np.add.reduce(a))
# 15
```