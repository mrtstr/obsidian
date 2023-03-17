- Reshape data (produce a “pivot” table) based on column values
- Uses unique values from specified index / columns to form axes of the resulting DataFrame
- `df[index, columns]` have to be unique
- can be reverted with [[pd melt]]
```python
pd.pivot(
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

# anki

START
Basic
[[pd pivot]]
- explaination
- parameters (3)
- condition
- how to revert
- example

| df1 | A | B | value | 
|---:|:----|:----|--------:| 
| 1 | A1 | B0 | 1 | 
| 2 | A1 | B1 | 2 | 
| 3 | A2 | B0 | 3 | 
| 4 | A2 | B1 | 4 |

Back: 
- Reshape data (produce a “pivot” table) based on column values
- Uses unique values from specified index / columns to form axes of the resulting DataFrame
- `df[index, columns]` have to be unique
- can be reverted with [[pd melt]]
```python
pd.pivot(
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
)
```

## example

| df1 | A | B | value | 
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

Tags: code, pandas
<!--ID: 1678872572562-->
END

START
Basic
[[pd pivot]] example:
| df1 | A | B | value | 
|---:|:----|:----|--------:| 
| 1 | A1 | B0 | 1 | 
| 2 | A1 | B1 | 2 | 
| 3 | A2 | B0 | 3 | 
| 4 | A2 | B1 | 4 |
```python
df1.pivot(index="A", columns="B", values="value")
```
Back: 
- Reshape data (produce a “pivot” table) based on column values
- Uses unique values from specified index / columns to form axes of the resulting DataFrame
- `df[index, columns]` have to be unique
- can be reverted with [[pd melt]]
```python
pd.pivot(
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
)
```

## example

| df1 | A | B | value | 
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

Tags: code, pandas
<!--ID: 1678872572565-->
END