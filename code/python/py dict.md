[[python]] [[py object]] [[hash map]]

```python
dict1 = {
	"A": 1,
	"B": 2,
	"C": 3,
	"D": 4,
}

dict2 = {
	"B": 12,
	"C": 13,
	"E": 14,
}

```

## dict.update
- overwrite all values with the values of the other dict
- only values not present in the other dict remain unchained
```python
dict1.update(dict2)
dict1
# {'A': 1, 'B': 12, 'C': 13, 'D': 4, 'E': 14}
```

```python
dict2.update(dict1)
dict2
# {'B': 2, 'C': 3, 'E': 14, 'A': 1, 'D': 4}
```

# Anki
START
Basic
what is the output, and what does the function do?

```python
dict1 = {
	"A": 1,
	"B": 2,
	"C": 3,
	"D": 4,
}

dict2 = {
	"B": 12,
	"C": 13,
	"E": 14,
}
```

```python
dict1.update(dict2)
dict1
```

```python
dict2.update(dict1)
dict2
```
Back: 

## dict.update
- overwrite all values with the values of the other dict
- only values not present in the other dict remain unchained
```python
dict1.update(dict2)
dict1
# {'A': 1, 'B': 12, 'C': 13, 'D': 4, 'E': 14}
```

```python
dict2.update(dict1)
dict2
# {'B': 2, 'C': 3, 'E': 14, 'A': 1, 'D': 4}
```

Tags: code python
<!--ID: 1698489556165-->
END