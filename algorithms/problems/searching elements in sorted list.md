### example finding element in sorted list:
```python
def bianry_search(x, sorted_list):
	minimum = 0
	maximum = len(sorted_list)
	while(True):
		guess= int((minimum+maximum)/2)
		if sorted_list[guess+1] > x and sorted_list[guess] <= x:
		return guess
		if sorted_list[guess] <= x:
		minimum = guess + 1
		if sorted_list[guess] > x:
		maximum = guess - 1
```



START
Basic
binary search: pseudo code example
Back: 
```python
def bianry_search(x):
	minimum = 0
	maximum = x
	while(True):
		guess= int((minimum+maximum)/2)
		if check_match(guess):
		return guess
		if check_too_high(guess):
		minimum = guess + 1
		if check_too_low(guess):
		maximum = guess - 1
```
Tags: algorithm problem
<!--ID: 1661591876816-->
END