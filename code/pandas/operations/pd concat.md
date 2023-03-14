- join [[pd dataframe|pd dataframes]] along the [[pd index]] or the [[pd column|pd columns]]
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

- `objs`: [[pd dataframe|pd dataframes]] or [[pd series]] that will be concatinated
- `axis`: {0- [[pd index]] (rows), 1- [[pd column]]}, default 0 - [[pd index]] (rows). The axis to concatenate along.
- `join`: {‘inner’, ‘outer’}, default ‘outer’. How to handle indexes on other axis(es). Outer for union and inner for intersection.
- `ignore_index`: replace the other index with a sequence 0, 1, ...
- `keys`: sequence, default None. Chreate a [[pd multiindex]] with the first level being the original dataframe it belongs to and the keys containing the names of the dataframes.

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

### along [[pd index]]
- can create [[pd index]] doublicates 
- combines the matching [[pd column|pd columns]] and creates matching partner with [[pd nan]] values for the remaining [[pd column|pd columns]] 
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

### along [[pd column|pd columns]]
- can create [[pd column]] doublicates 
- combines the matching [[pd index]] and creates matching partner with [[pd nan]] values for the remaining [[pd index]] 
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
### along [[pd index]]
- can create [[pd index]] doublicates 
- combines the matching [[pd column|pd columns]] and remove the rest of the [[pd column|pd columns]] 
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

### along [[pd column|pd columns]]
- can create [[pd column]] doublicates 
- combines the matching [[pd index]] and removes the rest of the rows
```python
pd.concat([df1, df2], axis=1, join="inner")
```
| | A | B | C | D | B | C | D | E | 
|---:|:----|:----|:----|:----|:----|:----|:----|:----| 
| 3 | A3 | B3 | C3 | D3 | B3 | C3 | D3 | E3 | 
| 4 | A4 | B4 | C4 | D4 | B4 | C4 | D4 | E4 | 

## create [[pd multiindex]] unsing keys
- create a [[pd multiindex]] with the first level being the original [[pd dataframe]] it belongs to and the keys containing the names of the dataframes
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
- join [[pd dataframe|pd dataframes]] along the [[pd index]] or the [[pd column|pd columns]]
- equivalent to [[np concat]]
```python
pd.concat(
    objs,
    axis=0,
    join="outer",
    ignore_index=False,
    keys=None,
)
```

- `objs`: [[pd dataframe|pd dataframes]] or [[pd series]] that will be concatinated
- `axis`: {0- [[pd index]] (rows), 1- [[pd column]]}, default 0 - [[pd index]] (rows). The axis to concatenate along.
- `join`: {‘inner’, ‘outer’}, default ‘outer’. How to handle indexes on other axis(es). Outer for union and inner for intersection.
- `ignore_index`: replace the other index with a sequence 0, 1, ...
- `keys`: sequence, default None. Chreate a [[pd multiindex]] with the first level being the original dataframe it belongs to and the keys containing the names of the dataframes.

Tags: code, pandas
<!--ID: 1678791381056-->
END


START
Basic
[[pd concat]] examples
- inner vs outer
- axis 0 vs 1
- using keys
Back: 
## [[pd concat]]
- join [[pd dataframe|pd dataframes]] along the [[pd index]] or the [[pd column|pd columns]]
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
### df1:
| | A | B | C | D | 
|---:|:----|:----|:----|:----| 
| 1 | A1 | B1 | C1 | D1 | 
| 2 | A2 | B2 | C2 | D2 | 
| 3 | A3 | B3 | C3 | D3 | 
| 4 | A4 | B4 | C4 | D4 |
### df2:
| | B | C | D | E | 
|---:|:----|:----|:----|:----|
| 3 | B3 | C3 | D3 | E3 | 
| 4 | B4 | C4 | D4 | E4 | 
| 5 | B5 | C5 | D5 | E5 | 
| 6 | B6 | C6 | D6 | E6 |

## outer join 
### along [[pd index]]
- can create [[pd index]] doublicates 
- combines the matching [[pd column|pd columns]] and creates matching partner with [[pd nan]] values for the remaining [[pd column|pd columns]] 
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

### along [[pd column|pd columns]]
- can create [[pd column]] doublicates 
- combines the matching [[pd index]] and creates matching partner with [[pd nan]] values for the remaining [[pd index]] 
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
### along [[pd index]]
- can create [[pd index]] doublicates 
- combines the matching [[pd column|pd columns]] and remove the rest of the [[pd column|pd columns]] 
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

### along [[pd column|pd columns]]
- can create [[pd column]] doublicates 
- combines the matching [[pd index]] and removes the rest of the rows
```python
pd.concat([df1, df2], axis=1, join="inner")
```
| | A | B | C | D | B | C | D | E | 
|---:|:----|:----|:----|:----|:----|:----|:----|:----| 
| 3 | A3 | B3 | C3 | D3 | B3 | C3 | D3 | E3 | 
| 4 | A4 | B4 | C4 | D4 | B4 | C4 | D4 | E4 | 

## create [[pd multiindex]] unsing keys
- create a [[pd multiindex]] with the first level being the original [[pd dataframe]] it belongs to and the keys containing the names of the dataframes
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