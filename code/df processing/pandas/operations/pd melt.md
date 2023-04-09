- undo / revert [[pd pivot]] operation

```python
pd.melt(
	df, 
	# df to unpivot
	id_vars=None, 
	# columns of df that will become combined will all value_vars
	value_vars=None, 
	# columns of df that will become combined will all id_vars
	# default use all columns not in id_vars 
)
```

# example

| df_pivot | B0 | B1 | 
|:----|-----:|-----:| 
| A1 | 1 | 2 | 
| A2 | 3 | 4 |
```python
df1_pivot = df1_pivot.reset_index()

```
| df1_pivot | A | B0 | B1 | 
|---:|:----|-----:|-----:| 
| 0 | A1 | 1 | 2 | 
| 1 | A2 | 3 | 4 |
```python
df1_pivot.melt(id_vars=["A"])
# use all columns not in id_vars as value_vars (B0 ad B1)
# is equal to the following
df1_pivot.melt(id_vars=["A"], value_vars=["B0", "B1"])
```
| | A | B | value | 
|---:|:----|:----|--------:| 
| 1 | A1 | B0 | 1 | 
| 2 | A1 | B1 | 2 | 
| 3 | A2 | B0 | 3 | 
| 4 | A2 | B1 | 4 |

```python
df1_pivot.melt(id_vars=["A"], value_vars=["B0"])
```
| | A | B | value | 
|---:|:----|:----|--------:| 
| 0 | A1 | B0 | 1 | 
| 1 | A2 | B0 | 3 |



# anki

START
Basic
how to undo a [[pd pivot]] operation with example

| df_pivot | B0 | B1 | 
|:----|-----:|-----:| 
| A1 | 1 | 2 | 
| A2 | 3 | 4 |

Back: 
[[pd melt]] can undo / revert [[pd pivot]] operation
```python
pd.melt(
	df, 
	# df to unpivot
	id_vars=None, 
	# columns of df that will become combined will all value_vars
	value_vars=None, 
	# columns of df that will become combined will all id_vars
	# default use all columns not in id_vars 
)
```
# example

| df_pivot | B0 | B1 | 
|:----|-----:|-----:| 
| A1 | 1 | 2 | 
| A2 | 3 | 4 |
```python
df1_pivot = df1_pivot.reset_index()

```
| df1_pivot | A | B0 | B1 | 
|---:|:----|-----:|-----:| 
| 0 | A1 | 1 | 2 | 
| 1 | A2 | 3 | 4 |
```python
df1_pivot.melt(id_vars=["A"])
# use all columns not in id_vars as value_vars (B0 ad B1)
# is equal to the following
df1_pivot.melt(id_vars=["A"], value_vars=["B0", "B1"])
```
| | A | B | value | 
|---:|:----|:----|--------:| 
| 1 | A1 | B0 | 1 | 
| 2 | A1 | B1 | 2 | 
| 3 | A2 | B0 | 3 | 
| 4 | A2 | B1 | 4 |

Tags: code, pandas
<!--ID: 1678872572555-->
END


START
Basic
[[pd melt]]
- explaination
- parameters
- example

| df1_pivot | A | B0 | B1 | 
|---:|:----|-----:|-----:| 
| 0 | A1 | 1 | 2 | 
| 1 | A2 | 3 | 4 |

```python
df1_pivot.melt(id_vars=["A"])
df1_pivot.melt(id_vars=["A"], value_vars=["B0", "B1"])
df1_pivot.melt(id_vars=["A"], value_vars=["B0"])
```

Back: 
- undo / revert [[pd pivot]] operation
```python
pd.melt(
	df, 
	# df to unpivot
	id_vars=None, 
	# columns of df that will become combined will all value_vars
	value_vars=None, 
	# columns of df that will become combined will all id_vars
	# default use all columns not in id_vars 
)
```

# example

| df1_pivot | A | B0 | B1 | 
|---:|:----|-----:|-----:| 
| 0 | A1 | 1 | 2 | 
| 1 | A2 | 3 | 4 |
```python
df1_pivot.melt(id_vars=["A"])
# use all columns not in id_vars as value_vars (B0 ad B1)
# is equal to the following
df1_pivot.melt(id_vars=["A"], value_vars=["B0", "B1"])
```
| | A | B | value | 
|---:|:----|:----|--------:| 
| 1 | A1 | B0 | 1 | 
| 2 | A1 | B1 | 2 | 
| 3 | A2 | B0 | 3 | 
| 4 | A2 | B1 | 4 |

```python
df1_pivot.melt(id_vars=["A"], value_vars=["B0"])
```
| | A | B | value | 
|---:|:----|:----|--------:| 
| 0 | A1 | B0 | 1 | 
| 1 | A2 | B0 | 3 |

Tags: code, pandas
<!--ID: 1678872572560-->
END