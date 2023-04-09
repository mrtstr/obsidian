# DataFrameGroupBy object
- Created by [[pd groupby]]
- [[py dict]] like data structure mapping group name to the [[pd index]] of group members applied on the [[pd dataframe]]

## attributes
- `.groups`: [[py dict]] containing the group names mapping to a [[py list]] of the [[pd index]] of its group members
- `.ngroups`: number of groups

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

### displaying group mapping and number of groups
```python
df.groupby("class").groups
# {
# 	'bird': ['falcon', 'parrot'], 
# 	'mammal': ['lion', 'monkey', 'leopard']
# }
df.groupby("class").ngroups
# 2
```
### iteration over grouped [[pd dataframe]]
```python
for name, group_df in df.groupby("class"):
	print(f"group name: {name}")
	print(f"group type: {type(group_df)}")
	print(group_df)
```
group name: bird 
group type: <class 'pandas.core.frame.DataFrame'>
| | class | order | max_speed | 
|:-------|:--------|:---------------|------------:| 
| falcon | bird | Falconiformes | 389 | 
| parrot | bird | Psittaciformes | 24 | 

group name: mammal 
group type: <class 'pandas.core.frame.DataFrame'>
| | class | order | max_speed | 
|:--------|:--------|:----------|------------:| 
| lion | mammal | Carnivora | 80.2 | 
| monkey | mammal | Primates | nan | 
| leopard | mammal | Carnivora | 58 |


### selecting a single grouped [[pd dataframe]]
```python
df.groupby("class").get_group("mammal")
```
| | class | order | max_speed | 
|:--------|:--------|:----------|------------:| 
| lion | mammal | Carnivora | 80.2 | 
| monkey | mammal | Primates | nan | 
| leopard | mammal | Carnivora | 58 |


# anki

START
Basic
[[pd DataFrameGroupBy]] object:
- attributes
- how to create it
- example: iterate over groups
- get sepecific group
Back: 
- Created by [[pd groupby]]
- [[py dict]] like data structure mapping group name to the [[pd index]] of group members applied on the [[pd dataframe]]

## attributes
- `.groups`: [[py dict]] containing the group names mapping to a [[py list]] of the [[pd index]] of its group members
- `.ngroups`: number of groups

## example

| | class | order | max_speed | 
|:--------|:--------|:---------------|------------:| 
| falcon | bird | Falconiformes | 389 | 
| parrot | bird | Psittaciformes | 24 | 
| lion | mammal | Carnivora | 80.2 | 
| monkey | mammal | Primates | nan | 
| leopard | mammal | Carnivora | 58 |

### displaying group mapping and number of groups
```python
df.groupby("class").groups
# {
# 	'bird': ['falcon', 'parrot'], 
# 	'mammal': ['lion', 'monkey', 'leopard']
# }
df.groupby("class").ngroups
# 2
```
### iteration over grouped [[pd dataframe]]
```python
for name, group_df in df.groupby("class"):
	print(f"group name: {name}")
	print(f"group type: {type(group_df)}")
	print(group_df)
```
group name: bird 
group type: <class 'pandas.core.frame.DataFrame'>
| | class | order | max_speed | 
|:-------|:--------|:---------------|------------:| 
| falcon | bird | Falconiformes | 389 | 
| parrot | bird | Psittaciformes | 24 | 

group name: mammal 
group type: <class 'pandas.core.frame.DataFrame'>
| | class | order | max_speed | 
|:--------|:--------|:----------|------------:| 
| lion | mammal | Carnivora | 80.2 | 
| monkey | mammal | Primates | nan | 
| leopard | mammal | Carnivora | 58 |


### selecting a single grouped [[pd dataframe]]
```python
df.groupby("class").get_group("mammal")
```
| | class | order | max_speed | 
|:--------|:--------|:----------|------------:| 
| lion | mammal | Carnivora | 80.2 | 
| monkey | mammal | Primates | nan | 
| leopard | mammal | Carnivora | 58 |

Tags: code, pandas
<!--ID: 1678964011867-->
END