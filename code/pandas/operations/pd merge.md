- joining two [[pd DataFrame|pd dataframe]] with [[pd Column|pd columns]] or [[pd Index]] as keys like in SQL
```python
pd.merge(
    left,
    # first dataframe or series to join
    right,
    # second df or series to join
    how="inner",
    # [[pd column]] or index level names to join on (most be in both)
    on=None,
    # [[pd column]] or index level names to join on (most be in both)
    left_on=None,
    right_on=None,
    # columns to use in the left and right df as keys
    # (same length requiered) 
    left_index=False,
    right_index=False,
    # if true use [[pd index]] as join key
    sort=True,
    # sort result after join keys. 
    # setting to false will increase speed.
    suffixes=("_x", "_y"),
    # A tuple of string suffixes to apply to overlapping columns.
    indicator=False,
    # add column that specifys if in both, just left or just right
    validate=None,
    # if specified, checks if merge is not of specified type throw error.
    # in {"1:1", "1:m", "m:1", "m:m"}
)
```

# example

```python
df1 = pd.DataFrame(
	{
		"A": ["A1", "A2", "A3", "A4"],
		"B": ["B1", "B2", "B3", "B4"],
		"C": ["C1", "C2", "C3", "C4"],
		"D": ["D1", "D2", "D3", "D4"],
	},
	index=[1, 2, 3, 4],
)

df2 = pd.DataFrame(
	{
		"A": ["A1", "N", "N", "N"],
		"B": ["N", "A2", "N", "N"],
		"C": ["N", "N", "A3", "N"],
		"D": ["N", "N", "N", "A4"],
	},
	index=[1, 2, 3, 4],
)
```
| df1 | A | B | C | D | 
|---:|:----|:----|:----|:----| 
| 1 | A1 | B1 | C1 | D1 | 
| 2 | A2 | B2 | C2 | D2 | 
| 3 | A3 | B3 | C3 | D3 | 
| 4 | A4 | B4 | C4 | D4 | 

| df2 | A | B | C | D | 
|---:|:----|:----|:----|:----| 
| 1 | A1 | N | N | N | 
| 2 | N | A2 | N | N | 
| 3 | N | N | A3 | N | 
| 4 | N | N | N | A4 |

## merge on [[pd Column]] with the same name
```python
pd.merge(df1, df2, on=["A"], how="outer")
```
| | A | B_x | C_x | D_x | B_y | C_y | D_y | 
|---:|:----|:------|:------|:------|:------|:------|:------| 
| 0 | A1 | B1 | C1 | D1 | N | N | N | 
| 1 | A2 | B2 | C2 | D2 | nan | nan | nan | 
| 2 | A3 | B3 | C3 | D3 | nan | nan | nan | 
| 3 | A4 | B4 | C4 | D4 | nan | nan | nan | 
| 4 | N | nan | nan | nan | A2 | N | N | 
| 5 | N | nan | nan | nan | N | A3 | N | 
| 6 | N | nan | nan | nan | N | N | A4 |

```python
pd.merge(df1, df2, on=["A"], how="inner")
```
| | A | B_x | C_x | D_x | B_y | C_y | D_y | 
|---:|:----|:------|:------|:------|:------|:------|:------| 
| 0 | A1 | B1 | C1 | D1 | N | N | N | 

## merge on [[pd Column]] with a different name
```python
pd.merge(df1, df2, left_on=["A"], right_on=["B"], how="inner")
```
| | A_x | B_x | C_x | D_x | A_y | B_y | C_y | D_y | 
|---:|:------|:------|:------|:------|:------|:------|:------|:------| 
| 0 | A2 | B2 | C2 | D2 | N | A2 | N | N |

# anki

START
Basic
[[pandas]] [[pd merge]]
- general concept
- parameters (12)
Back: 
- joining two [[pd DataFrame|pd dataframe]] with [[pd Column|pd columns]] or [[pd Index]] as keys like in SQL
```python
pd.merge(
    left,
    # first dataframe or series to join
    right,
    # second df or series to join
    how="inner",
    # [[pd column]] or index level names to join on (most be in both)
    on=None,
    # [[pd column]] or index level names to join on (most be in both)
    left_on=None,
    right_on=None,
    # columns to use in the left and right df as keys
    # (same length requiered) 
    left_index=False,
    right_index=False,
    # if true use [[pd index]] as join key
    sort=True,
    # sort result after join keys. 
    # setting to false will increase speed.
    suffixes=("_x", "_y"),
    # A tuple of string suffixes to apply to overlapping columns.
    indicator=False,
    # add column that specifys if in both, just left or just right
    validate=None,
    # if specified, checks if merge is not of specified type throw error.
    # in {"1:1", "1:m", "m:1", "m:m"}
)
```

Tags: code, pandas
<!--ID: 1678802210303-->
END

START
Basic
[[pandas]]
- how to make [[pd merge]] faster?
Back: 
- set sort=False (default is True)
- disables sorting after merged keys
- will improve speed
Tags: code, pandas
<!--ID: 1678802210306-->
END


START
Basic
[[pandas]]: [[pd merge]]
- how to validate relationships after [[pd merge]]
Back: 
use parameter `validate`: 
- If specified, checks if merge is not of specified type throw error.
- default None. 
- “one_to_one” or “1:1”: checks if merge keys are unique in both left and right datasets.
- “one_to_many” or “1:m”: checks if merge keys are unique in left dataset.
- “many_to_one” or “m:1”: checks if merge keys are unique in right dataset.
- “many_to_many” or “m:m”: allowed, but does not result in checks.

Tags: code, pandas
<!--ID: 1678802210308-->
END


START
Basic
[[pandas]]: [[pd merge]] examples
```python
pd.merge(df1, df2, on=["A"], how="outer")

pd.merge(df1, df2, on=["A"], how="inner")

pd.merge(df1, df2, left_on=["A"], right_on=["B"], how="inner")
```

```python
df1 = pd.DataFrame(
	{
		"A": ["A1", "A2", "A3", "A4"],
		"B": ["B1", "B2", "B3", "B4"],
		"C": ["C1", "C2", "C3", "C4"],
		"D": ["D1", "D2", "D3", "D4"],
	},
	index=[1, 2, 3, 4],
)

df2 = pd.DataFrame(
	{
		"A": ["A1", "N", "N", "N"],
		"B": ["N", "A2", "N", "N"],
		"C": ["N", "N", "A3", "N"],
		"D": ["N", "N", "N", "A4"],
	},
	index=[1, 2, 3, 4],
)
```
| df1 | A | B | C | D | 
|---:|:----|:----|:----|:----| 
| 1 | A1 | B1 | C1 | D1 | 
| 2 | A2 | B2 | C2 | D2 | 
| 3 | A3 | B3 | C3 | D3 | 
| 4 | A4 | B4 | C4 | D4 | 

| df2 | A | B | C | D | 
|---:|:----|:----|:----|:----| 
| 1 | A1 | N | N | N | 
| 2 | N | A2 | N | N | 
| 3 | N | N | A3 | N | 
| 4 | N | N | N | A4 |


Back: 

## merge on [[pd Column]] with the same name
```python
pd.merge(df1, df2, on=["A"], how="outer")
```
| | A | B_x | C_x | D_x | B_y | C_y | D_y | 
|---:|:----|:------|:------|:------|:------|:------|:------| 
| 0 | A1 | B1 | C1 | D1 | N | N | N | 
| 1 | A2 | B2 | C2 | D2 | nan | nan | nan | 
| 2 | A3 | B3 | C3 | D3 | nan | nan | nan | 
| 3 | A4 | B4 | C4 | D4 | nan | nan | nan | 
| 4 | N | nan | nan | nan | A2 | N | N | 
| 5 | N | nan | nan | nan | N | A3 | N | 
| 6 | N | nan | nan | nan | N | N | A4 |

```python
pd.merge(df1, df2, on=["A"], how="inner")
```
| | A | B_x | C_x | D_x | B_y | C_y | D_y | 
|---:|:----|:------|:------|:------|:------|:------|:------| 
| 0 | A1 | B1 | C1 | D1 | N | N | N | 

## merge on [[pd Column]] with a different name
```python
pd.merge(df1, df2, left_on=["A"], right_on=["B"], how="inner")
```
| | A_x | B_x | C_x | D_x | A_y | B_y | C_y | D_y | 
|---:|:------|:------|:------|:------|:------|:------|:------|:------| 
| 0 | A2 | B2 | C2 | D2 | N | A2 | N | N |

Tags: code, pandas
<!--ID: 1678802210309-->
END