- performes operations on columns or rows of [[pd DataFrame]] or a [[pd DataFrameGroupBy]] objects 
- operations take a row or a column and return a single value
	-> mapping (vector -> scalar)
- can perform multiple functions at once

```python
df.agg(
   func=None, 
   axis=0,
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

## used on [[pd DataFrameGroupBy]]

### named aggragation
```python
df.groupby("class").agg(
	max_max_speed = pd.NamedAgg(column="max_speed", aggfunc="max"),
	min_max_speed = pd.NamedAgg(column="max_speed", aggfunc="min"),
)

df.groupby("class").agg(
	max_max_speed = ("max_speed", "max"),
	min_max_speed = ("max_speed", "min"),
)
```
| class | max_max_speed | min_max_speed | 
|:--------|----------------:|----------------:| 
| bird | 389 | 24 | 
| mammal | 80.2 | 58 |


### apply multiple custom function
```python
def max_len(group):
	l = [
		len(i) if isinstance(i, str) else 1 
		for i in group
	]
return max(l)

def get_list(group):
	return list(group)

df.groupby("class").agg([get_list, max_len])
```
| class | ('order', 'get_list') | ('order', 'max_len') | ('max_speed', 'get_list') | ('max_speed', 'max_len') | 
|:--------|:---------------------------------------|-----------------------:|:----------------------------|---------------------------:| 
| bird | ['Falconiformes', 'Psittaciformes'] | 14 | [389.0, 24.0] | 1 | 
| mammal | ['Carnivora', 'Primates', 'Carnivora'] | 9 | [80.2, nan, 58.0] | 1 |



## used on [[pd DataFrame]]
```python
df.agg(["sum", "count", "nunique"], axis=0)
```

| | class | order | max_speed | 
|:--------|:--------------------|:----------------------|------------:| 
| sum | birdbirdmammalmammalmammal | FalconiformesPsittaciformesCarnivoraPrimatesCarnivora | 551.2 | 
| count | 5 | 5 | 4 | 
| nunique | 2 | 4 | 4 |

```python
df.agg(["count", "nunique"], axis=1)
```
| | count | nunique | 
|:--------|--------:|----------:| 
| falcon | 3 | 3 | 
| parrot | 3 | 3 | 
| lion | 3 | 3 | 
| monkey | 2 | 2 | 
| leopard | 3 | 3 |


# anki

START
Basic
[[pd agg]]
- how and when to use
- parameters
- simple example

| | class | order | max_speed | 
|:--------|:--------|:---------------|------------:| 
| falcon | bird | Falconiformes | 389 | 
| parrot | bird | Psittaciformes | 24 | 
| lion | mammal | Carnivora | 80.2 | 
| monkey | mammal | Primates | nan | 
| leopard | mammal | Carnivora | 58 |

```python
df.groupby("class").agg(["max", "min"])
df.agg(["sum", "count", "nunique"], axis=0)
```

Back: 
- performes operations on columns or rows of [[pd DataFrame]] or a [[pd DataFrameGroupBy]] objects 
- operations take a row or a column and return a single value
	-> mapping (vector -> scalar)
- can perform multiple functions at once

```python
df.agg(
   func=None, 
   axis=0,
)
```

### example

| | class | order | max_speed | 
|:--------|:--------|:---------------|------------:| 
| falcon | bird | Falconiformes | 389 | 
| parrot | bird | Psittaciformes | 24 | 
| lion | mammal | Carnivora | 80.2 | 
| monkey | mammal | Primates | nan | 
| leopard | mammal | Carnivora | 58 |

#### used on [[pd DataFrameGroupBy]]

```python
df.groupby("class").agg(["max", "min"])
```
| class | ('order', 'max') | ('order', 'min') | ('max_speed', 'max') | ('max_speed', 'min') | 
|:--------|:-------------------|:-------------------|-----------------------:|-----------------------:| 
| bird | Psittaciformes | Falconiformes | 389 | 24 | 
| mammal | Primates | Carnivora | 80.2 | 58 |


#### used on [[pd DataFrame]]
```python
df.agg(["sum", "count", "nunique"], axis=0)
```

| | class | order | max_speed | 
|:--------|:--------------------|:----------------------|------------:| 
| sum | birdbirdmammalmammalmammal | FalconiformesPsittaciformesCarnivoraPrimatesCarnivora | 551.2 | 
| count | 5 | 5 | 4 | 
| nunique | 2 | 4 | 4 |


Tags: code, pandas
<!--ID: 1678969456505-->
END

START
Basic
example: 
- given the following [[pd DataFrame]]
- create a [[pd DataFrame]] that contains
- for every class: lengh of the longest strings and a list of entrys

| | class | order | max_speed | 
|:--------|:--------|:---------------|------------:| 
| falcon | bird | Falconiformes | 389 | 
| parrot | bird | Psittaciformes | 24 | 
| lion | mammal | Carnivora | 80.2 | 
| monkey | mammal | Primates | nan | 
| leopard | mammal | Carnivora | 58 |

Back: 

```python
def max_len(group):
	l = [
		len(i) if isinstance(i, str) else 1 
		for i in group
	]
return max(l)

def get_list(group):
	return list(group)

df.groupby("class").agg([get_list, max_len])
```
| class | ('order', 'get_list') | ('order', 'max_len') | ('max_speed', 'get_list') | ('max_speed', 'max_len') | 
|:--------|:---------------------------------------|-----------------------:|:----------------------------|---------------------------:| 
| bird | ['Falconiformes', 'Psittaciformes'] | 14 | [389.0, 24.0] | 1 | 
| mammal | ['Carnivora', 'Primates', 'Carnivora'] | 9 | [80.2, nan, 58.0] | 1 |

Tags: code, pandas
<!--ID: 1678969456507-->
END


START
Basic
```python

def max_len(group):
	l = [
		len(i) if isinstance(i, str) else 1 
		for i in group
	]
return max(l)

def get_list(group):
	return list(group)

df.groupby("class").agg([get_list, max_len])
df.agg(["sum", "count", "nunique"], axis=0)
df.agg(["count", "nunique"], axis=1)
```

| | class | order | max_speed | 
|:--------|:--------|:---------------|------------:| 
| falcon | bird | Falconiformes | 389 | 
| parrot | bird | Psittaciformes | 24 | 
| lion | mammal | Carnivora | 80.2 | 
| monkey | mammal | Primates | nan | 
| leopard | mammal | Carnivora | 58 |

Back: 

```python
def max_len(group):
	l = [
		len(i) if isinstance(i, str) else 1 
		for i in group
	]
return max(l)

def get_list(group):
	return list(group)

df.groupby("class").agg([get_list, max_len])
```

| class | ('order', 'get_list') | ('order', 'max_len') | ('max_speed', 'get_list') | ('max_speed', 'max_len') | 
|:--------|:---------------------------------------|-----------------------:|:----------------------------|---------------------------:| 
| bird | ['Falconiformes', 'Psittaciformes'] | 14 | [389.0, 24.0] | 1 | 
| mammal | ['Carnivora', 'Primates', 'Carnivora'] | 9 | [80.2, nan, 58.0] | 1 |

```python
df.agg(["sum", "count", "nunique"], axis=0)
```

| | class | order | max_speed | 
|:--------|:--------------------|:----------------------|------------:| 
| sum | birdbirdmammalmammalmammal | FalconiformesPsittaciformesCarnivoraPrimatesCarnivora | 551.2 | 
| count | 5 | 5 | 4 | 
| nunique | 2 | 4 | 4 |

```python
df.agg(["count", "nunique"], axis=1)
```
| | count | nunique | 
|:--------|--------:|----------:| 
| falcon | 3 | 3 | 
| parrot | 3 | 3 | 
| lion | 3 | 3 | 
| monkey | 2 | 2 | 
| leopard | 3 | 3 |

Tags: code, pandas
<!--ID: 1678969456509-->
END


START
Basic
- [[pandas]] names aggegation of the following [[pd DataFrame]]
- two ways of getting a [[pd DataFrame]] containing the maximum and numimim of max_speed per class

| | class | order | max_speed | 
|:--------|:--------|:---------------|------------:| 
| falcon | bird | Falconiformes | 389 | 
| parrot | bird | Psittaciformes | 24 | 
| lion | mammal | Carnivora | 80.2 | 
| monkey | mammal | Primates | nan | 
| leopard | mammal | Carnivora | 58 |

Back: 
```python
df.groupby("class").agg(
	max_max_speed = pd.NamedAgg(column="max_speed", aggfunc="max"),
	min_max_speed = pd.NamedAgg(column="max_speed", aggfunc="min"),
)

df.groupby("class").agg(
	max_max_speed = ("max_speed", "max"),
	min_max_speed = ("max_speed", "min"),
)
```
| class | max_max_speed | min_max_speed | 
|:--------|----------------:|----------------:| 
| bird | 389 | 24 | 
| mammal | 80.2 | 58 |

Tags: code, pandas
<!--ID: 1678974652763-->
END