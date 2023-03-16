given the following [[pd DataFrame]]

| | class | order | max_speed | 
|:--------|:--------|:---------------|------------:| 
| falcon | bird | Falconiformes | 389 | 
| parrot | bird | Psittaciformes | 24 | 
| lion | mammal | Carnivora | 80.2 | 
| monkey | mammal | Primates | nan | 
| leopard | mammal | Carnivora | 58 |

- create a [[pd DataFrameGroupBy]] object by applying the function [[pd groupby]]
- use `.discribe()`
```python
df.groupby("class").describe()
```
| class | ('max_speed', 'count') | ('max_speed', 'mean') | ('max_speed', 'std') | ('max_speed', 'min') | ('max_speed', '25%') | ('max_speed', '50%') | ('max_speed', '75%') | ('max_speed', 'max') | 
|:--------|-------------------------:|------------------------:|-----------------------:|-----------------------:|-----------------------:|-----------------------:|-----------------------:|-----------------------:| 
| bird | 2 | 206.5 | 258.094 | 24 | 115.25 | 206.5 | 297.75 | 389 | | mammal | 2 | 69.1 | 15.6978 | 58 | 63.55 | 69.1 | 74.65 | 80.2 |

# anki

START
Basic
get a summary of a [[pd DataFrameGroupBy]] object
Back: 
given the following [[pd DataFrame]]

| | class | order | max_speed | 
|:--------|:--------|:---------------|------------:| 
| falcon | bird | Falconiformes | 389 | 
| parrot | bird | Psittaciformes | 24 | 
| lion | mammal | Carnivora | 80.2 | 
| monkey | mammal | Primates | nan | 
| leopard | mammal | Carnivora | 58 |

- create a [[pd DataFrameGroupBy]] object by applying the function [[pd groupby]]
- use `.discribe()`
```python
df.groupby("class").describe()
```
| class | ('max_speed', 'count') | ('max_speed', 'mean') | ('max_speed', 'std') | ('max_speed', 'min') | ('max_speed', '25%') | ('max_speed', '50%') | ('max_speed', '75%') | ('max_speed', 'max') | 
|:--------|-------------------------:|------------------------:|-----------------------:|-----------------------:|-----------------------:|-----------------------:|-----------------------:|-----------------------:| 
| bird | 2 | 206.5 | 258.094 | 24 | 115.25 | 206.5 | 297.75 | 389 | | mammal | 2 | 69.1 | 15.6978 | 58 | 63.55 | 69.1 | 74.65 | 80.2 |

Tags: code, pandas
<!--ID: 1678964011891-->
END