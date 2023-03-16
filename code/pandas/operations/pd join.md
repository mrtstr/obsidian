- join [[pd DataFrame|pd dataframes]] or [[pd Series]] on [[pd Column]] or [[pd Index]]
- less prowerful but more convenient version of [[pd merge]]

```python
DataFrame.join(
	other, 
	# join partner df
	on=None,
	# key of list of keys to join on
	how='left',
	# in {‘left’, ‘right’, ‘outer’, ‘inner’} 
	lsuffix='', 
	# suffix to put on columns of left df
	rsuffix='', 
	# suffix to put on columns of right df
	sort=False, 
	# sort after join columns (costs perfoemance)
	validate=None
    # if specified, checks if merge is not of specified type throw error.
    # in {"1:1", "1:m", "m:1", "m:m"}
)
```

## difference to [[pd merge]]
- no suffix per default ([[pd merge]]: default ("x_", "y_"))
- default is "left" ([[pd merge]]: default "inner")
- no sorting per default ([[pd merge]]: sorting per default true)
- joining only on [[pd Column|pd columns]] with the same name possible ([[pd merge]]: different names possible)

the following functions are doing exactly the same:
```python
df1.join(df2, on=["key1", "key2"])

pd.merge(
    left=df1, 
    right=df2, 
    left_on=["key1", "key2"], 
    right_index=True, 
    how="left", 
    sort=False
)
```


START
Basic
[[pd join]]
- usage
- diffence to [[pd merge]]
- parameters (7)
Back: 
- join [[pd DataFrame|pd dataframes]] or [[pd Series]] on [[pd Column]] or [[pd Index]]
- less prowerful but more convenient version of [[pd merge]]

```python
DataFrame.join(
	other, 
	# join partner df
	on=None,
	# key of list of keys to join on
	how='left',
	# in {‘left’, ‘right’, ‘outer’, ‘inner’} 
	lsuffix='', 
	# suffix to put on columns of left df
	rsuffix='', 
	# suffix to put on columns of right df
	sort=False, 
	# sort after join columns (costs perfoemance)
	validate=None
    # if specified, checks if merge is not of specified type throw error.
    # in {"1:1", "1:m", "m:1", "m:m"}
)
```
Tags: code, pandas
<!--ID: 1678804499731-->
END

START
Basic
difference of [[pd join]] to [[pd merge]]
- why is it needed?
- differences
- identical example
Back: 
- [[pd join]] is a less prowerful but more convenient version of [[pd merge]]

### differences:
- no suffix per default ([[pd merge]]: default ("x_", "y_"))
- default is "left" ([[pd merge]]: default "inner")
- no sorting per default ([[pd merge]]: sorting per default true)
- joining only on [[pd Column|pd columns]] with the same name possible ([[pd merge]]: different names possible)

#### identical example
the following functions are doing exactly the same:
```python
df1.join(df2, on=["key1", "key2"])

pd.merge(
    left=df1, 
    right=df2, 
    left_on=["key1", "key2"], 
    right_index=True, 
    how="left", 
    sort=False
)
```
Tags: code, pandas
<!--ID: 1678804499735-->
END