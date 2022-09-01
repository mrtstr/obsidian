### Approach
- searching for element in ordered list 
- if it's possible to check if any element is too high or too low in $\mathcal{O}(1)$ 
- in $\mathcal{O}(log(n))$ 

### algorithm
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


START
Basic
binary search: complexity and when to use.
Back: 
- searching for element in ordered list 
- if it's possible to check if any element is too high or too low in $\mathcal{O}(1)$ 
- in $\mathcal{O}(log(n))$ 
Tags: algorithms, approach
<!--ID: 1661591876811-->
END

