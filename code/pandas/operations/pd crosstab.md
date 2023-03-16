- like [[pd pivot_table]] but takes [[py interatable]] or [[pd Series]] as input instead of a [[pd DataFrame]]
```python
pd.crosstab(
	index, 
	# unique value's interatable of will become the new index
	columns, 
	# unique value's interatable of will become the new columns
	values=None, 
	# values to use the aggregate function on
	# if not specified: count frequency
	aggfunc=None, 
	# how to aggregate values
	# only when values are given
	margins=False, 
	# add a row and a cloumn with sums
	dropna=True, 
	# remove columns with only Nones
	normalize=False
	# values in {all, index, columns}
)
```

# examples
## without values and aggfunc ⇾ frequency of occurence
```python
pd.crosstab(
	columns=["x", "x", "y","z"],
	index=["a", "a", "b", "c"],
	margins=True,
)
```
|  | x | y | z | All | 
|:--------|----:|----:|----:|------:| 
| a | 2 | 0 | 0 | 2 | 
| b | 0 | 1 | 0 | 1 | 
| c | 0 | 0 | 1 | 1 | 
| All | 2 | 1 | 1 | 4 |

```python
pd.crosstab(
	columns=["x", "x", "y","z"],
	index=["a", "a", "b", "c"],
	normalize="all", # in {all, index, columns}
	margins=True,
)
```
|  | x | y | z | All | 
|:--------|----:|-----:|-----:|------:| 
| a | 0.5 | 0 | 0 | 0.5 | 
| b | 0 | 0.25 | 0 | 0.25 | 
| c | 0 | 0 | 0.25 | 0.25 | 
| All | 0.5 | 0.25 | 0.25 | 1 |

## with values and aggfunc ⇾ aggrage values

```python
pd.crosstab(
	columns=["A", "A", "B", "B"],
	index=["X", "X", "Y", "X"],
	values=[1, 2, 4, 8],
	aggfunc="sum",
	margins=True
)
```

| row_0 | A | B | All | 
|:--------|----:|----:|------:| 
| X | 3 | 8 | 11 | 
| Y | nan | 4 | 4 | 
| All | 3 | 12 | 15 |


# anki


START
Basic
[[pd crosstab]]
- usage
- parameter
Back: 
- like [[pd pivot_table]] but takes [[py interatable]] or [[pd Series]] as input instead of a [[pd DataFrame]]
```python
pd.crosstab(
	index, 
	# unique value's interatable of will become the new index
	columns, 
	# unique value's interatable of will become the new columns
	values=None, 
	# values to use the aggregate function on
	# if not specified: count frequency
	aggfunc=None, 
	# how to aggregate values
	# only when values are given
	margins=False, 
	# add a row and a cloumn with sums
	dropna=True, 
	# remove columns with only Nones
	normalize=False
	# values in {all, index, columns}
)
```

# examples
## without values and aggfunc ⇾ frequency of occurence
```python
pd.crosstab(
	columns=["x", "x", "y","z"],
	index=["a", "a", "b", "c"],
	margins=True,
)
```
|  | x | y | z | All | 
|:--------|----:|----:|----:|------:| 
| a | 2 | 0 | 0 | 2 | 
| b | 0 | 1 | 0 | 1 | 
| c | 0 | 0 | 1 | 1 | 
| All | 2 | 1 | 1 | 4 |

```python
pd.crosstab(
	columns=["x", "x", "y","z"],
	index=["a", "a", "b", "c"],
	normalize="all", # in {all, index, columns}
	margins=True,
)
```
|  | x | y | z | All | 
|:--------|----:|-----:|-----:|------:| 
| a | 0.5 | 0 | 0 | 0.5 | 
| b | 0 | 0.25 | 0 | 0.25 | 
| c | 0 | 0 | 0.25 | 0.25 | 
| All | 0.5 | 0.25 | 0.25 | 1 |

## with values and aggfunc ⇾ aggrage values

```python
pd.crosstab(
	columns=["A", "A", "B", "B"],
	index=["X", "X", "Y", "X"],
	values=[1, 2, 4, 8],
	aggfunc="sum",
	margins=True
)
```

| row_0 | A | B | All | 
|:--------|----:|----:|------:| 
| X | 3 | 8 | 11 | 
| Y | nan | 4 | 4 | 
| All | 3 | 12 | 15 |

Tags: code, pandas
<!--ID: 1678893330023-->
END


START
Basic
```python
pd.crosstab(
	columns=["x", "x", "y","z"],
	index=["a", "a", "b", "c"],
	margins=True,
)

pd.crosstab(
	columns=["x", "x", "y","z"],
	index=["a", "a", "b", "c"],
	normalize="all", # in {all, index, columns}
	margins=True,
)

pd.crosstab(
	columns=["A", "A", "B", "B"],
	index=["X", "X", "Y", "X"],
	values=[1, 2, 4, 8],
	aggfunc="sum",
	margins=True
)
```
Back: 

## without values and aggfunc ⇾ frequency of occurence
```python
pd.crosstab(
	columns=["x", "x", "y","z"],
	index=["a", "a", "b", "c"],
	margins=True,
)
```
|  | x | y | z | All | 
|:--------|----:|----:|----:|------:| 
| a | 2 | 0 | 0 | 2 | 
| b | 0 | 1 | 0 | 1 | 
| c | 0 | 0 | 1 | 1 | 
| All | 2 | 1 | 1 | 4 |

```python
pd.crosstab(
	columns=["x", "x", "y","z"],
	index=["a", "a", "b", "c"],
	normalize="all", # in {all, index, columns}
	margins=True,
)
```
|  | x | y | z | All | 
|:--------|----:|-----:|-----:|------:| 
| a | 0.5 | 0 | 0 | 0.5 | 
| b | 0 | 0.25 | 0 | 0.25 | 
| c | 0 | 0 | 0.25 | 0.25 | 
| All | 0.5 | 0.25 | 0.25 | 1 |

## with values and aggfunc ⇾ aggrage values

```python
pd.crosstab(
	columns=["A", "A", "B", "B"],
	index=["X", "X", "Y", "X"],
	values=[1, 2, 4, 8],
	aggfunc="sum",
	margins=True
)
```

| row_0 | A | B | All | 
|:--------|----:|----:|------:| 
| X | 3 | 8 | 11 | 
| Y | nan | 4 | 4 | 
| All | 3 | 12 | 15 |

Tags: code, pandas
<!--ID: 1678893330026-->
END