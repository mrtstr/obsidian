
- Reshape data (produce a “pivot” table) based on column values
- Uses unique values from specified index / columns to form axes of the resulting DataFrame
- `df[index, columns]` can have duplicates and will be aggregated
- [[pd pivot]] in comparison can not deal with duplicates in `df[index, columns]`

```python
pd.pivot_table(
	df,
	# dataframe to transform
	index=None, 
	# column name of df
	# its unique values will become the index of the new df
	columns=None, 
	# column name of df
	# its unique values will become the columns of the new df
	values=None
	# column name of df that 
	# will become the values to fill the new df
	aggfunc=np.mean,
	# function to aggregate dublicates
	fill_value=None,
	# value to fill missing values with
	dropna=True
	# Do not include columns whose entries are all NaN
)
```
## example

```python

df1 = pd.DataFrame(
	{
		"A": ["A1", "A1", "A2", "A2"],
		"B": ["B0", "B1", "B0", "B1"],
		"value": [1, 2, 3, 4],
	},
	index=[1, 2, 3, 4],
)
```
| df1 | A | B | value | 
|---:|:----|:----|--------:| 
| 1 | A1 | B0 | 1 | 
| 2 | A1 | B1 | 2 | 
| 3 | A2 | B0 | 3 | 
| 4 | A2 | B1 | 4 |

```python
df1=pd.concat([df1, df1])
# create duplicates
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

```python
df1.pivot_table(index="A", columns="B", values="value", aggfunc='sum')
# add up the duplices
```
| A | B0 | B1 | 
|:----|-----:|-----:| 
| A1 | 2 | 4 | 
| A2 | 6 | 8 |


```python
df1.pivot_table(index="A", columns="B", values="value", aggfunc='count')
# two values per value combination of A and B
```
| A | B0 | B1 | 
|:----|-----:|-----:| 
| A1 | 2 | 2 | 
| A2 | 2 | 2 |

```python
df1.pivot_table(index="A", columns="B", values="value")
# same behavour as pd.pivot since default is mean
# and duplicates are identical
```
| A | B0 | B1 | 
|:----|-----:|-----:| 
| A1 | 1 | 2 | 
| A2 | 3 | 4 |


# anki

START
Basic
[[pd pivot_table]]
- explaination
- parameters (6)
- difference to [[pd pivot]]
Back: 
- Reshape data (produce a “pivot” table) based on column values
- Uses unique values from specified index / columns to form axes of the resulting DataFrame
- `df[index, columns]` can have duplicates and will be aggregated
- [[pd pivot]] in comparison can not deal with duplicates in `df[index, columns]`
```python
pd.pivot_table(
	df,
	# dataframe to transform
	index=None, 
	# column name of df
	# its unique values will become the index of the new df
	columns=None, 
	# column name of df
	# its unique values will become the columns of the new df
	values=None
	# column name of df that 
	# will become the values to fill the new df
	aggfunc=np.mean,
	# function to aggregate dublicates
	fill_value=None,
	# value to fill missing values with
	dropna=True
	# Do not include columns whose entries are all NaN
)
```
Tags: code, pandas
<!--ID: 1678873985238-->
END

START
Basic
[[pd pivot_table]] example

```python
df1.pivot_table(index="A", columns="B", values="value", aggfunc='sum')
df1.pivot_table(index="A", columns="B", values="value", aggfunc='count')
df1.pivot_table(index="A", columns="B", values="value")
```

| df1 | A | B | value | 
|---:|:----|:----|--------:| 
| 1 | A1 | B0 | 1 | 
| 2 | A1 | B1 | 2 | 
| 3 | A2 | B0 | 3 | 
| 4 | A2 | B1 | 4 |

```python
df1=pd.concat([df1, df1])
# create duplicates
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

Back: 
```python
df1.pivot_table(index="A", columns="B", values="value", aggfunc='sum')
# add up the duplices
```
| A | B0 | B1 | 
|:----|-----:|-----:| 
| A1 | 2 | 4 | 
| A2 | 6 | 8 |

```python
df1.pivot_table(index="A", columns="B", values="value", aggfunc='count')
# two values per value combination of A and B
```
| A | B0 | B1 | 
|:----|-----:|-----:| 
| A1 | 2 | 2 | 
| A2 | 2 | 2 |

```python
df1.pivot_table(index="A", columns="B", values="value")
# same behavour as pd.pivot since default is mean
# and duplicates are identical
```
| A | B0 | B1 | 
|:----|-----:|-----:| 
| A1 | 1 | 2 | 
| A2 | 3 | 4 |


Tags: code, pandas
<!--ID: 1678873985241-->
END