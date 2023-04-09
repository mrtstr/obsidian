### Background
- check all combinations of list elements without repeating an element and without order
- $n \choose k$ combinations ([[combinations - no repeat, no order]])

### algorithm
```python
for index1 in range(len(my_list)):
	for index2 in range(index1+1, len(my_list)):
		for index3 in range(index2+1, len(my_list)):
			...
				check({my_list[index1], my_list[index2], my_list[index3], ...})
```

START
Basic
- brute force: all combinations no repeat, no order
- algorithm and number of combinations

Back: 
- $n \choose k$ combinations
```python
for index1 in range(len(my_list)):
	for index2 in range(index1+1, len(my_list)):
		for index3 in range(index2+1, len(my_list)):
			...
				check({my_list[index1], my_list[index2], my_list[index3], ...})
```
Tags: algorithm approach
<!--ID: 1662064277858-->
END