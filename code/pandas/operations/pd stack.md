# pd stack
- move level of column [[pd MultiIndex]] to the row [[pd MultiIndex]]
- transforms [[pd DataFrame]] to [[pd DataFrame]] (if column and row index length > 0) or [[pd Series]] if one axis has a zero length index
```python
df.stack(
   level=- 1, 
   # level of column multiindex to move to row multiindex
   # default: last level
   fill_value=None,
)
```
# pd unstack
- move level of row [[pd MultiIndex]] to the column [[pd MultiIndex]]
```python
df.unstack(
   level=- 1, 
   # level of row multiindex to move to column multiindex
   # default: last level
   fill_value=None,
)
```
# example
```python
df1 = pd.DataFrame(
	data={
		"A": list(range(4)),
		"B": list(range(4,8)),
		"C": list(range(8,12)),
	},
	index=pd.MultiIndex.from_product([["a", "b"], ["x", "y"]])
)
```
|  | A | B | C | 
|:-----------|----:|----:|----:| 
| ('a', 'x') | 0 | 4 | 8 | 
| ('a', 'y') | 1 | 5 | 9 | 
| ('b', 'x') | 2 | 6 | 10 | 
| ('b', 'y') | 3 | 7 | 11 |

```python
df1.unstack(0)
```
| | ('A', 'a') | ('A', 'b') | ('B', 'a') | ('B', 'b') | ('C', 'a') | ('C', 'b') | 
|:---|-------------:|-------------:|-------------:|-------------:|-------------:|-------------:| 
| x | 0 | 2 | 4 | 6 | 8 | 10 | 
| y | 1 | 3 | 5 | 7 | 9 | 11 |

```python
df1.unstack(1)
```
| | ('A', 'x') | ('A', 'y') | ('B', 'x') | ('B', 'y') | ('C', 'x') | ('C', 'y') | 
|:---|-------------:|-------------:|-------------:|-------------:|-------------:|-------------:| 
| a | 0 | 1 | 4 | 5 | 8 | 9 | 
| b | 2 | 3 | 6 | 7 | 10 | 11 |

```python
df1.unstack(0).unstack(0)
# both row index levels are unstacked
# -> create series
```
| | 0 | 
|:----------------|----:| 
| ('A', 'a', 'x') | 0 | 
| ('A', 'a', 'y') | 1 | 
| ('A', 'b', 'x') | 2 | 
| ('A', 'b', 'y') | 3 | 
| ('B', 'a', 'x') | 4 | 
| ('B', 'a', 'y') | 5 | 
| ('B', 'b', 'x') | 6 | 
| ('B', 'b', 'y') | 7 | 
| ('C', 'a', 'x') | 8 | 
| ('C', 'a', 'y') | 9 | 
| ('C', 'b', 'x') | 10 | 
| ('C', 'b', 'y') | 11 |

# anki

START
Basic
[[pd stack|pd stack and unstack]] 
- usage
- parameters
- example
|  | A | B | C | 
|:-----------|----:|----:|----:| 
| ('a', 'x') | 0 | 4 | 8 | 
| ('a', 'y') | 1 | 5 | 9 | 
| ('b', 'x') | 2 | 6 | 10 | 
| ('b', 'y') | 3 | 7 | 11 |
```python
df1.unstack(0)
df1.stack()
```

Back: 
# pd stack
- move level of column [[pd MultiIndex]] to the row [[pd MultiIndex]]
- transforms [[pd DataFrame]] to [[pd DataFrame]] (if column and row index length > 0) or [[pd Series]] if one axis has a zero length index
```python
df.stack(
   level=- 1, 
   # level of column multiindex to move to row multiindex
   # default: last level
   fill_value=None,
)
```
# pd unstack
- move level of row [[pd MultiIndex]] to the column [[pd MultiIndex]]

```python
df1.unstack(0)
```
| | ('A', 'a') | ('A', 'b') | ('B', 'a') | ('B', 'b') | ('C', 'a') | ('C', 'b') | 
|:---|-------------:|-------------:|-------------:|-------------:|-------------:|-------------:| 
| x | 0 | 2 | 4 | 6 | 8 | 10 | 
| y | 1 | 3 | 5 | 7 | 9 | 11 |

```python
df1.stack()
```
| | 0 | 
|:----------------|----:| 
| ('a', 'x', 'A') | 0 | 
| ('a', 'x', 'B') | 4 | 
| ('a', 'x', 'C') | 8 | 
| ('a', 'y', 'A') | 1 | 
| ('a', 'y', 'B') | 5 | 
| ('a', 'y', 'C') | 9 | 
| ('b', 'x', 'A') | 2 | 
| ('b', 'x', 'B') | 6 | 
| ('b', 'x', 'C') | 10 | 
| ('b', 'y', 'A') | 3 | 
| ('b', 'y', 'B') | 7 | 
| ('b', 'y', 'C') | 11 |

Tags: code, pandas
<!--ID: 1678885894648-->
END



START
Basic

|  | A | B | C | 
|:-----------|----:|----:|----:| 
| ('a', 'x') | 0 | 4 | 8 | 
| ('a', 'y') | 1 | 5 | 9 | 
| ('b', 'x') | 2 | 6 | 10 | 
| ('b', 'y') | 3 | 7 | 11 |
```python
df1.unstack(0).unstack(0)
df1.unstack(1).unstack(0)
df1.stack()
```
Back: 

```python
df1.unstack(0).unstack(0)
```
| | 0 | 
|:----------------|----:| 
| ('A', 'a', 'x') | 0 | 
| ('A', 'a', 'y') | 1 | 
| ('A', 'b', 'x') | 2 | 
| ('A', 'b', 'y') | 3 | 
| ('B', 'a', 'x') | 4 | 
| ('B', 'a', 'y') | 5 | 
| ('B', 'b', 'x') | 6 | 
| ('B', 'b', 'y') | 7 | 
| ('C', 'a', 'x') | 8 | 
| ('C', 'a', 'y') | 9 | 
| ('C', 'b', 'x') | 10 | 
| ('C', 'b', 'y') | 11 | 

```python
df1.unstack(1).unstack(0)
```
| | 0 |
|:----------------|----:| 
| ('A', 'x', 'a') | 0 | 
| ('A', 'x', 'b') | 2 | 
| ('A', 'y', 'a') | 1 | 
| ('A', 'y', 'b') | 3 | 
| ('B', 'x', 'a') | 4 | 
| ('B', 'x', 'b') | 6 | 
| ('B', 'y', 'a') | 5 | 
| ('B', 'y', 'b') | 7 | 
| ('C', 'x', 'a') | 8 | 
| ('C', 'x', 'b') | 10 | 
| ('C', 'y', 'a') | 9 | 
| ('C', 'y', 'b') | 11 |

```python
df1.stack()
```
| | 0 |
|:----------------|----:| 
| ('A', 'x', 'a') | 0 | 
| ('A', 'x', 'b') | 2 | 
| ('A', 'y', 'a') | 1 | 
| ('A', 'y', 'b') | 3 | 
| ('B', 'x', 'a') | 4 | 
| ('B', 'x', 'b') | 6 | 
| ('B', 'y', 'a') | 5 | 
| ('B', 'y', 'b') | 7 | 
| ('C', 'x', 'a') | 8 | 
| ('C', 'x', 'b') | 10 | 
| ('C', 'y', 'a') | 9 | 
| ('C', 'y', 'b') | 11 |

Tags: code, pandas
<!--ID: 1678885894650-->
END


START
Basic
do a [[transpose]] operation on the following [[pd DataFrame]] without using `df.T` or [[pd transpose]]
| | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 1 | 5 | 9 | 
| b | 2 | 6 | 10 | 
| c | 3 | 7 | 11 | 
| d | 4 | 8 | 12 |

Back: 
```python
df.stack().unstack(0)
```
| | a | b | c | d | 
|:-----|----:|----:|----:|----:| 
| col1 | 1 | 2 | 3 | 4 | 
| col2 | 5 | 6 | 7 | 8 | 
| col3 | 9 | 10 | 11 | 12 |

Tags: code, pandas
<!--ID: 1678885894653-->
END