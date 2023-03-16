- Concatinate (do a [[union]]) [[pd DataFrame|pd dataframes]] along the [[pd Index]] or the [[pd Column|pd columns]]
- on the other axis do a [[intersection]] (inner) or a [[union]] (outer)
- equivalent to [[np concat]]
```python
pd.concat(
    objs,
    # df or series that will be concatinated
    axis=0,
    # {0->index (rows), 1->columns}
    # The axis to concatenate along
    join="outer",
    # How to handle indexes on other axis(es)
    # Outer for union and inner for intersection.
    # in {‘inner’, ‘outer’}
    ignore_index=False,
    # replace the other index with a sequence 0, 1, ...
    keys=None,
    # in set create multiindex 
	# first level being the name of origin dataframe 
	# keys containing the names of the dataframes.
    levels=None,
    names=None,
    verify_integrity=False,
    # Check whether the new concatenated axis contains duplicates
)
```

# examples

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
		"B": ["B3", "B4", "B5", "B6"],
		"C": ["C3", "C4", "C5", "C6"],
		"D": ["D3", "D4", "D5", "D6"],
		"E": ["E3", "E4", "E5", "E6"],
	},
	index=[3, 4, 5, 6],
)
```
| | A | B | C | D | 
|---:|:----|:----|:----|:----| 
| 1 | A1 | B1 | C1 | D1 | 
| 2 | A2 | B2 | C2 | D2 | 
| 3 | A3 | B3 | C3 | D3 | 
| 4 | A4 | B4 | C4 | D4 |

| | B | C | D | E | 
|---:|:----|:----|:----|:----|
| 3 | B3 | C3 | D3 | E3 | 
| 4 | B4 | C4 | D4 | E4 | 
| 5 | B5 | C5 | D5 | E5 | 
| 6 | B6 | C6 | D6 | E6 |

## outer join 

### along [[pd Index]]
- concatinate the rows (do a union)
- combines the matching [[pd Column|pd columns]] and creates matching partner with [[pd NaN]] values for the remaining [[pd Column|pd columns]] 
```python
pd.concat([df1, df2], axis=0, join="outer")
```
| | A | B | C | D | E | 
|---:|:----|:----|:----|:----|:----| 
| 1 | A1 | B1 | C1 | D1 | nan | 
| 2 | A2 | B2 | C2 | D2 | nan | 
| 3 | A3 | B3 | C3 | D3 | nan | 
| 4 | A4 | B4 | C4 | D4 | nan | 
| 3 | nan | B3 | C3 | D3 | E3 | 
| 4 | nan | B4 | C4 | D4 | E4 | 
| 5 | nan | B5 | C5 | D5 | E5 | 
| 6 | nan | B6 | C6 | D6 | E6 |

### along [[pd Column|pd columns]]
- concatinate the columns (do a union)
- combines the matching [[pd Index]] and creates matching partner with [[pd NaN]] values for the remaining [[pd Index]] 
```python
pd.concat([df1, df2], axis=1, join="outer")
```
| | A | B | C | D | B | C | D | E | 
|---:|:----|:----|:----|:----|:----|:----|:----|:----| 
| 1 | A1 | B1 | C1 | D1 | nan | nan | nan | nan | 
| 2 | A2 | B2 | C2 | D2 | nan | nan | nan | nan | 
| 3 | A3 | B3 | C3 | D3 | B3 | C3 | D3 | E3 | 
| 4 | A4 | B4 | C4 | D4 | B4 | C4 | D4 | E4 | 
| 5 | nan | nan | nan | nan | B5 | C5 | D5 | E5 | 
| 6 | nan | nan | nan | nan | B6 | C6 | D6 | E6 |

## innter join
### along [[pd Index]]
- concatinate the rows (do a union)
- combines the matching [[pd Column|pd columns]] and remove the rest of the [[pd Column|pd columns]] 
```python
pd.concat([df1, df2], axis=0, join="inner")
```
| | B | C | D | 
|---:|:----|:----|:----| 
| 1 | B1 | C1 | D1 | 
| 2 | B2 | C2 | D2 | 
| 3 | B3 | C3 | D3 | 
| 4 | B4 | C4 | D4 | 
| 3 | B3 | C3 | D3 | 
| 4 | B4 | C4 | D4 | 
| 5 | B5 | C5 | D5 | 
| 6 | B6 | C6 | D6 |

### along [[pd Column|pd columns]]
- concatinate the [[pd Column|pd columns]] (do a union)
- combines the matching [[pd Index]] and removes the rest of the rows
```python
pd.concat([df1, df2], axis=1, join="inner")
```
| | A | B | C | D | B | C | D | E | 
|---:|:----|:----|:----|:----|:----|:----|:----|:----| 
| 3 | A3 | B3 | C3 | D3 | B3 | C3 | D3 | E3 | 
| 4 | A4 | B4 | C4 | D4 | B4 | C4 | D4 | E4 | 

## create [[pd MultiIndex]] unsing keys
- create a [[pd MultiIndex]] with the first level being the original [[pd DataFrame]] it belongs to and the keys containing the names of the dataframes
```python
pd.concat([df1, df2], axis=1, join="outer", keys=["df1", "df2"])
```
| | ('df1', 'A') | ('df1', 'B') | ('df1', 'C') | ('df1', 'D') | ('df2', 'B') | ('df2', 'C') | ('df2', 'D') | ('df2', 'E') | 
|---:|:---------------|:---------------|:---------------|:---------------|:---------------|:---------------|:---------------|:---------------| 
| 1 | A1 | B1 | C1 | D1 | nan | nan | nan | nan | 
| 2 | A2 | B2 | C2 | D2 | nan | nan | nan | nan | 
| 3 | A3 | B3 | C3 | D3 | B3 | C3 | D3 | E3 | 
| 4 | A4 | B4 | C4 | D4 | B4 | C4 | D4 | E4 | 
| 5 | nan | nan | nan | nan | B5 | C5 | D5 | E5 | 
| 6 | nan | nan | nan | nan | B6 | C6 | D6 | E6 |


# Anki

START
Basic
[[pd concat]]
- definition
- parameters
Back: 
- Concatinate [[pd DataFrame|pd dataframes]] (do a union) along the [[pd Index]] or the [[pd Column|pd columns]]
- on the other axis do a [[intersection]] (inner) or a union (outer)
- equivalent to [[np concat]]
```python
pd.concat(
    objs,
    # df or series that will be concatinated
    axis=0,
    # {0->index (rows), 1->columns}
    # The axis to concatenate along
    join="outer",
    # How to handle indexes on other axis(es)
    # Outer for union and inner for intersection.
    # in {‘inner’, ‘outer’}
    ignore_index=False,
    # replace the other index with a sequence 0, 1, ...
    keys=None,
    # in set create multiindex 
	# first level being the name of origin dataframe 
	# keys containing the names of the dataframes.
    levels=None,
    names=None,
    verify_integrity=False,
    # Check whether the new concatenated axis contains duplicates
)
```
Tags: code, pandas
<!--ID: 1678791381056-->
END


START
Basic
[[pd concat]] examples
```python
pd.concat([df1, df2], axis=0, join="outer")

pd.concat([df1, df2], axis=1, join="outer")

pd.concat([df1, df2], axis=0, join="inner")

pd.concat([df1, df2], axis=1, join="inner")

pd.concat([df1, df2], axis=1, join="outer", keys=["df1", "df2"])

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
		"B": ["B3", "B4", "B5", "B6"],
		"C": ["C3", "C4", "C5", "C6"],
		"D": ["D3", "D4", "D5", "D6"],
		"E": ["E3", "E4", "E5", "E6"],
	},
	index=[3, 4, 5, 6],
)
```
| | A | B | C | D | 
|---:|:----|:----|:----|:----| 
| 1 | A1 | B1 | C1 | D1 | 
| 2 | A2 | B2 | C2 | D2 | 
| 3 | A3 | B3 | C3 | D3 | 
| 4 | A4 | B4 | C4 | D4 |

| | B | C | D | E | 
|---:|:----|:----|:----|:----|
| 3 | B3 | C3 | D3 | E3 | 
| 4 | B4 | C4 | D4 | E4 | 
| 5 | B5 | C5 | D5 | E5 | 
| 6 | B6 | C6 | D6 | E6 |


Back: 
## [[pd concat]]
- Concatinate [[pd DataFrame|pd dataframes]] (do a union) along the [[pd Index]] or the [[pd Column|pd columns]]
- on the other axis do a [[intersection]] (inner) or a union (outer)
- equivalent to [[np concat]]
```python
pd.concat(
    objs,
    axis=0,
    join="outer",
    ignore_index=False,
    keys=None,
    levels=None,
    names=None,
    verify_integrity=False,
    copy=True,
)
```
# examples

## outer join 

### along [[pd Index]]
- concatinate the rows (do a union)
- combines the matching [[pd Column|pd columns]] and creates matching partner with [[pd NaN]] values for the remaining [[pd Column|pd columns]] 
```python
pd.concat([df1, df2], axis=0, join="outer")
```
| | A | B | C | D | E | 
|---:|:----|:----|:----|:----|:----| 
| 1 | A1 | B1 | C1 | D1 | nan | 
| 2 | A2 | B2 | C2 | D2 | nan | 
| 3 | A3 | B3 | C3 | D3 | nan | 
| 4 | A4 | B4 | C4 | D4 | nan | 
| 3 | nan | B3 | C3 | D3 | E3 | 
| 4 | nan | B4 | C4 | D4 | E4 | 
| 5 | nan | B5 | C5 | D5 | E5 | 
| 6 | nan | B6 | C6 | D6 | E6 |

### along [[pd Column|pd columns]]
- concatinate the columns (do a union)
- combines the matching [[pd Index]] and creates matching partner with [[pd NaN]] values for the remaining [[pd Index]] 
```python
pd.concat([df1, df2], axis=1, join="outer")
```
| | A | B | C | D | B | C | D | E | 
|---:|:----|:----|:----|:----|:----|:----|:----|:----| 
| 1 | A1 | B1 | C1 | D1 | nan | nan | nan | nan | 
| 2 | A2 | B2 | C2 | D2 | nan | nan | nan | nan | 
| 3 | A3 | B3 | C3 | D3 | B3 | C3 | D3 | E3 | 
| 4 | A4 | B4 | C4 | D4 | B4 | C4 | D4 | E4 | 
| 5 | nan | nan | nan | nan | B5 | C5 | D5 | E5 | 
| 6 | nan | nan | nan | nan | B6 | C6 | D6 | E6 |

## innter join
### along [[pd Index]]
- concatinate the rows (do a union)
- combines the matching [[pd Column|pd columns]] and remove the rest of the [[pd Column|pd columns]] 
```python
pd.concat([df1, df2], axis=0, join="inner")
```
| | B | C | D | 
|---:|:----|:----|:----| 
| 1 | B1 | C1 | D1 | 
| 2 | B2 | C2 | D2 | 
| 3 | B3 | C3 | D3 | 
| 4 | B4 | C4 | D4 | 
| 3 | B3 | C3 | D3 | 
| 4 | B4 | C4 | D4 | 
| 5 | B5 | C5 | D5 | 
| 6 | B6 | C6 | D6 |

### along [[pd Column|pd columns]]
- concatinate the [[pd Column|pd columns]] (do a union)
- combines the matching [[pd Index]] and removes the rest of the rows
```python
pd.concat([df1, df2], axis=1, join="inner")
```
| | A | B | C | D | B | C | D | E | 
|---:|:----|:----|:----|:----|:----|:----|:----|:----| 
| 3 | A3 | B3 | C3 | D3 | B3 | C3 | D3 | E3 | 
| 4 | A4 | B4 | C4 | D4 | B4 | C4 | D4 | E4 | 

## create [[pd MultiIndex]] unsing keys
- create a [[pd MultiIndex]] with the first level being the original [[pd DataFrame]] it belongs to and the keys containing the names of the dataframes
```python
pd.concat([df1, df2], axis=1, join="outer", keys=["df1", "df2"])
```
| | ('df1', 'A') | ('df1', 'B') | ('df1', 'C') | ('df1', 'D') | ('df2', 'B') | ('df2', 'C') | ('df2', 'D') | ('df2', 'E') | 
|---:|:---------------|:---------------|:---------------|:---------------|:---------------|:---------------|:---------------|:---------------| 
| 1 | A1 | B1 | C1 | D1 | nan | nan | nan | nan | 
| 2 | A2 | B2 | C2 | D2 | nan | nan | nan | nan | 
| 3 | A3 | B3 | C3 | D3 | B3 | C3 | D3 | E3 | 
| 4 | A4 | B4 | C4 | D4 | B4 | C4 | D4 | E4 | 
| 5 | nan | nan | nan | nan | B5 | C5 | D5 | E5 | 
| 6 | nan | nan | nan | nan | B6 | C6 | D6 | E6 |

Tags: code, pandas
<!--ID: 1678791381064-->
END