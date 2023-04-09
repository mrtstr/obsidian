## [[pd pivot]]: create pivot table
- unique value's column of [[pd dataframe]] will become the new [[pd index]]
- unique value's column of [[pd dataframe]] will become the new [[pd column|pd columns]]
- `df[index, columns]` have to be unique

### example
```
| | A | B | value | 
|---:|:----|:----|--------:| 
| 1 | A1 | B0 | 1 | 
| 2 | A1 | B1 | 2 | 
| 3 | A2 | B0 | 3 | 
| 4 | A2 | B1 | 4 |

```python
df1.pivot(index="A", columns="B", values="value")
```
|  | B0 | B1 | 
|:----|-----:|-----:| 
| A1 | 1 | 2 | 
| A2 | 3 | 4 |

## [[pd pivot_table]]
- like [[pd pivot]] but can deal with duplicates in `df[index, columns]` by aggregating them
### example
```
| df1 | A | B | value | 
|---:|:----|:----|--------:| 
| 1 | A1 | B0 | 1 | 
| 2 | A1 | B1 | 2 | 
| 3 | A2 | B0 | 3 | 
| 4 | A2 | B1 | 4 |
| 1 | A1 | B0 | 1 | 
| 2 | A1 | B1 | 2 | 
| 3 | A2 | B0 | 3 | 
| 4 | A2 | B1 | 4 |
```
```python
df1.pivot_table(index="A", columns="B", values="value", aggfunc='sum')
# add up the duplices
```
| A | B0 | B1 | 
|:----|-----:|-----:| 
| A1 | 2 | 4 | 
| A2 | 6 | 8 |

## [[pd melt]]
- undo a [[pd pivot]] operation
### example

|  | A | B0 | B1 | 
|---:|:----|-----:|-----:| 
| 0 | A1 | 1 | 2 | 
| 1 | A2 | 3 | 4 |
```python
df1_pivot.melt(id_vars=["A"])
```
| | A | B | value | 
|---:|:----|:----|--------:| 
| 1 | A1 | B0 | 1 | 
| 2 | A1 | B1 | 2 | 
| 3 | A2 | B0 | 3 | 
| 4 | A2 | B1 | 4 |

## [[pd stack]]
- move level of column [[pd multiindex]] to the row [[pd multiindex]]
- transforms [[pd dataframe]] to [[pd dataframe]] (if column and row index length > 0) or [[pd series]] if one axis has a zero length index

## pd unstack
- move level of row [[pd multiindex]] to the column [[pd multiindex]]
### example
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


# anki


START
Basic
[[pandas]] methods to rearrange [[pd dataframe]] (5)
- short explaining
- simple example
Back: 
## [[pd pivot]]: create pivot table
- unique value's column of [[pd dataframe]] will become the new [[pd index]]
- unique value's column of [[pd dataframe]] will become the new [[pd column|pd columns]]
- `df[index, columns]` have to be unique

### example

| | A | B | value | 
|---:|:----|:----|--------:| 
| 1 | A1 | B0 | 1 | 
| 2 | A1 | B1 | 2 | 
| 3 | A2 | B0 | 3 | 
| 4 | A2 | B1 | 4 |

```python
df1.pivot(index="A", columns="B", values="value")
```
|  | B0 | B1 | 
|:----|-----:|-----:| 
| A1 | 1 | 2 | 
| A2 | 3 | 4 |

## [[pd pivot_table]]
- like [[pd pivot]] but can deal with duplicates in `df[index, columns]` by aggregating them
### example
```
| df1 | A | B | value | 
|---:|:----|:----|--------:| 
| 1 | A1 | B0 | 1 | 
| 2 | A1 | B1 | 2 | 
| 3 | A2 | B0 | 3 | 
| 4 | A2 | B1 | 4 |
| 1 | A1 | B0 | 1 | 
| 2 | A1 | B1 | 2 | 
| 3 | A2 | B0 | 3 | 
| 4 | A2 | B1 | 4 |
```
```python
df1.pivot_table(index="A", columns="B", values="value", aggfunc='sum')
# add up the duplices
```
| A | B0 | B1 | 
|:----|-----:|-----:| 
| A1 | 2 | 4 | 
| A2 | 6 | 8 |

## [[pd melt]]
- undo a [[pd pivot]] operation
### example

|  | A | B0 | B1 | 
|---:|:----|-----:|-----:| 
| 0 | A1 | 1 | 2 | 
| 1 | A2 | 3 | 4 |
```python
df1_pivot.melt(id_vars=["A"])
```
| | A | B | value | 
|---:|:----|:----|--------:| 
| 1 | A1 | B0 | 1 | 
| 2 | A1 | B1 | 2 | 
| 3 | A2 | B0 | 3 | 
| 4 | A2 | B1 | 4 |

## [[pd stack]]
- move level of column [[pd multiindex]] to the row [[pd multiindex]]
- transforms [[pd dataframe]] to [[pd dataframe]] (if column and row index length > 0) or [[pd series]] if one axis has a zero length index

## pd unstack
- move level of row [[pd multiindex]] to the column [[pd multiindex]]
### example
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


Tags: code, pandas
<!--ID: 1678885894641-->
END