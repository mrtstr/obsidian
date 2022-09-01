### all combinations no repeat, no order
check all (orderless) combinations of list elements without repeating an element
```python
for index1 in range(len(my_list)):
	for index2 in range(index1+1, len(my_list)):
		for index3 in range(index2+1, len(my_list)):
			...
				check({my_list[index1], my_list[index2], my_list[index3], ...})
```