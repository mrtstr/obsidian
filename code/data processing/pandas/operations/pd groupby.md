- Creates a [[pd DataFrameGroupBy]] object
- splitting a [[pd dataframe]] based on mapping ([[py dict]], [[pd series]], [[pd column]])

![[pd DataFrameGroupBy#DataFrameGroupBy object]]

```python
df.groupby(
   by=None, 
   # mapping index -> group
   # given direct mapping as dict/series or columns to group by
   # [col1, col2] interpreted as index -> values of (col1, col2)
   axis=0, 
   # dimension to split along
   # 0 -> group index, 1 -> group columns
   level=None, 
   # if axis is a multiindex
   as_index=True, 
   # use group labels as index
   sort=True, 
   # Sort group keys
   # use false for better performance
   group_keys=NoDefault.no_default, 
   squeeze=NoDefault.no_default, 
   observed=False, 
   dropna=True
)
```

# example
```python
df = pd.DataFrame(
	[
		("bird", "Falconiformes", 389.0),
		("bird", "Psittaciformes", 24.0),
		("mammal", "Carnivora", 80.2),
		("mammal", "Primates", np.nan),
		("mammal", "Carnivora", 58),
	],
	index=["falcon", "parrot", "lion", "monkey", "leopard"],
	columns=("class", "order", "max_speed"),
)
```
| | class | order | max_speed | 
|:--------|:--------|:---------------|------------:| 
| falcon | bird | Falconiformes | 389 | 
| parrot | bird | Psittaciformes | 24 | 
| lion | mammal | Carnivora | 80.2 | 
| monkey | mammal | Primates | nan | 
| leopard | mammal | Carnivora | 58 |

## selecting columns
```python
df.groupby("class")["max_speed"].agg("min")
# equal to
df["max_speed"].groupby(df["class"]).agg("min")
```
| class | max_speed | 
|:--------|------------:| 
| bird | 24 | 
| mammal | 58 |
## using a [[pd column]] to split
```python
df.groupby("class")["max_speed"].agg(["max", "min"])
```
| class | max | min | 
|:--------|------:|------:| 
| bird | 389 | 24 | 
| mammal | 80.2 | 58 |

## using a [[py dict]] to split
```python
df.groupby({
	"falcon": "non cat",
	"leopard": "cat",
	"lion": "cat",
	"monkey": "non cat",
	"parrot": "non cat",
})["max_speed"].agg(["max", "min"])
```
| | max | min | 
|:--------|------:|------:| 
| cat | 80.2 | 58 | 
| non cat | 389 | 24 |

## make [[pd index]] unique
- use [[pd index]] as mapping for the split with [[pd groupby]]
- take the first value if there are duplicates

| | class | order | max_speed | 
|:--------|:--------|:---------------|------------:| 
| falcon | bird | Falconiformes | 389 | 
| parrot | bird | Psittaciformes | 24 | 
| lion | mammal | Carnivora | 80.2 | 
| monkey | mammal | Primates | nan | 
| leopard | mammal | Carnivora | 58 | 
| monkey | mammal | Primates | nan |

```python
df2.groupby(df2.index).agg("first")
```

| | class | order | max_speed | 
|:--------|:--------|:---------------|------------:| 
| falcon | bird | Falconiformes | 389 | 
| leopard | mammal | Carnivora | 58 | 
| lion | mammal | Carnivora | 80.2 | 
| monkey | mammal | Primates | nan | 
| parrot | bird | Psittaciformes | 24 |

# anki

START
Basic
[[pd groupby]]
- Discription
- What does it create?
- Parameters (2)
Back: 
- Creates a [[pd DataFrameGroupBy]] object
- splitting a [[pd dataframe]] based on mapping ([[py dict]], [[pd series]], [[pd column]])


### DataFrameGroupBy object
- Created by [[pd groupby]]
- [[py dict]] like data structure mapping group name to the [[pd index]] of group members applied on the [[pd dataframe]]

#### attributes
- `.groups`: [[py dict]] containing the group names mapping to a [[py list]] of the [[pd index]] of its group members
- `.ngroups`: number of groups

### parameters
```python
df.groupby(
   by=None, 
   # mapping index -> group
   # given direct mapping as dict/series or columns to group by
   # [col1, col2] interpreted as index -> values of (col1, col2)
   axis=0, 
   # dimension to split along
   # 0 -> group index, 1 -> group columns
   level=None, 
   # if axis is a multiindex
   as_index=True, 
   # use group labels as index
   sort=True, 
   # Sort group keys
   # use false for better performance
   group_keys=NoDefault.no_default, 
   squeeze=NoDefault.no_default, 
   observed=False, 
   dropna=True
)
```
Tags: code pandas
<!--ID: 1678964011875-->
END


START
Basic
[[pd groupby]] example
- using [[pd column]] class to split
- using [[py dict]] to split cats and non cats
and give the min and max value of the speed

| | class | order | max_speed | 
|:--------|:--------|:---------------|------------:| 
| falcon | bird | Falconiformes | 389 | 
| parrot | bird | Psittaciformes | 24 | 
| lion | mammal | Carnivora | 80.2 | 
| monkey | mammal | Primates | nan | 
| leopard | mammal | Carnivora | 58 |

Back: 
## using a [[pd column]] to split
```python
df.groupby("class")["max_speed"].agg(["max", "min"])
```
| class | max | min | 
|:--------|------:|------:| 
| bird | 389 | 24 | 
| mammal | 80.2 | 58 |

## using a [[py dict]] to split
```python
df.groupby({
	"falcon": "non cat",
	"leopard": "cat",
	"lion": "cat",
	"monkey": "non cat",
	"parrot": "non cat",
})["max_speed"].agg(["max", "min"])
```
| | max | min | 
|:--------|------:|------:| 
| cat | 80.2 | 58 | 
| non cat | 389 | 24 |

Tags: code pandas
<!--ID: 1678964011878-->
END


START
Basic
[[pd groupby]] to make [[pd index]] inique
Back: 
- use [[pd index]] as mapping for the split with [[pd groupby]]
- take the first value if there are duplicates

| | class | order | max_speed | 
|:--------|:--------|:---------------|------------:| 
| falcon | bird | Falconiformes | 389 | 
| parrot | bird | Psittaciformes | 24 | 
| lion | mammal | Carnivora | 80.2 | 
| monkey | mammal | Primates | nan | 
| leopard | mammal | Carnivora | 58 | 
| monkey | mammal | Primates | nan |

```python
df2.groupby(df2.index).agg("first")
```

| | class | order | max_speed | 
|:--------|:--------|:---------------|------------:| 
| falcon | bird | Falconiformes | 389 | 
| leopard | mammal | Carnivora | 58 | 
| lion | mammal | Carnivora | 80.2 | 
| monkey | mammal | Primates | nan | 
| parrot | bird | Psittaciformes | 24 |

Tags: code pandas
<!--ID: 1678964011881-->
END
