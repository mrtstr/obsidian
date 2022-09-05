```python
def a():
	x = 3
	def b():
		x = x + 1
		print(x)
	b()
a()
```


```python
def a():
	x = 3
	def b():
		print(x)
	b()
a()
```