- Replace the values of a [[pd series]] or a [[pd dataframe]] with the values of another but only then [[pd index]] (and [[pd column]]) are matching 
- if `overwrite=False` is set only null values are overwritting
- different behavour than the update in a [[py dict]] which is even adding new keys if not present in dict1

## [[pd update]] unsave behavour
- when updating a [[pd slicing|slice]] with different data type it does not work because of the [[pd view and copy behavour]] of [[pandas]]

![[pd view and copy behavour#pd view and copy behavour]]

#### on a slice with an update that is changing the data type [[pd update]] has no effect
```python
series1["A":"C"].update({"A": 77.7})
# A 1 
# B 2 
# C 3 
# D 4 
# E 5
```

#### on a slice with an updatewithout data type change [[pd update]] works
```python
series1["A":"C"].update({"A": 77})
# A 77 
# B 2 
# C 3 
# D 4 
# E 5
```


#### on a non sliced object up, update allways works
```python
series1.update({"A": 77})
# A 77.7 
# B 2 
# C 3 
# D 4 
# E 5
```

#### how to make it save
```python
series1_splice = series1["A":"C"].copy()
series1_splice.update({"A": 77.7})
series1["A":"C"] = series1_splice
# A 77.7 
# B 2 
# C 3 
# D 4 
# E 5
```

## examples
```python
series1 = pd.Series({
	"A": 1,
	"B": 2,
	"C": 3,
	"D": 4,
	"E": 5,
})

series2 = pd.Series({
	"A": 11,
	"C": None,
	"D": 13,
	"F": 14,
}, name="col1")
```

```python
series1.update(series2)
series1
# A 11 
# B 2 
# C 3 
# D 12
# E 5
```

```python
df1 = pd.DataFrame({
	"col1":{
		"A": 1,
		"B": 2,
		"C": None,
		"D": None
	},
	"col2":{
		"A": 5,
		"B": 6,
		"C": 7,
		"D": 8,
	},
})
```

|     | col1 | col2 |
|:--- | ----:| ----:|
| A   |    1 |    5 |
| B   |    2 |    6 |
| C   |    nan |    7 |
| D   |    nan |    8 |


```python
df1.update(series2, overwrite=False)
df1
```

| | col1 | col2 | 
|:---|-------:|-------:| 
| A | 1 | 5 | 
| B | 2 | 6 | 
| C | nan | 7 | 
| D | 13 | 8 |


```python
df1.update(series2) # overwrite=True is default
df1
```

| | col1 | col2 | 
|:---|-------:|-------:| 
| A | 11 | 5 | 
| B | 2 | 6 | 
| C | nan | 7 | 
| D | 13 | 8 |

# Anki
START
Basic

[[pd update]]
- definition
- difference to [[py dict]].update
- why is it unsave and how to make it save
- examples
 
```python
series1.update(series2)
series1
```

```python
df1.update(series2, overwrite=False)
df1
```

```python
df1.update(series2) 
df1
```

```python
series1 = pd.Series({
	"A": 1,
	"B": 2,
	"C": 3,
	"D": 4,
	"E": 5,
})

series2 = pd.Series({
	"A": 11,
	"C": None,
	"D": 13,
	"F": 14,
}, name="col1")
```

```python
df1 = pd.DataFrame({
	"col1":{
		"A": 1,
		"B": 2,
		"C": None,
		"D": None
	},
	"col2":{
		"A": 5,
		"B": 6,
		"C": 7,
		"D": 8,
	},
})
```

|     | col1 | col2 |
|:--- | ----:| ----:|
| A   |    1 |    5 |
| B   |    2 |    6 |
| C   |    nan |    7 |
| D   |    nan |    8 |


Back: 
- Replace the values of a [[pd series]] or a [[pd dataframe]] with the values of another but only then [[pd index]] (and [[pd column]]) are matching 
- if `overwrite=False` is set only null values are overwritting
- different behavour than the update in a [[py dict]] which is even adding new keys if not present in dict1

```python
series1.update(series2)
series1
# A 11 
# B 2 
# C 3 
# D 12
# E 5
```

```python
df1.update(series2, overwrite=False)
df1
```

| | col1 | col2 | 
|:---|-------:|-------:| 
| A | 1 | 5 | 
| B | 2 | 6 | 
| C | nan | 7 | 
| D | 13 | 8 |

```python
df1.update(series2) # overwrite=True is default
df1
```

| | col1 | col2 | 
|:---|-------:|-------:| 
| A | 11 | 5 | 
| B | 2 | 6 | 
| C | nan | 7 | 
| D | 13 | 8 |

Tags: code pandas
<!--ID: 1698489556143-->
END


START
Basic

[[pd update]]
- definition
- why is it unsave?
- how to make it save

Back: 
### Definition
- Replace the values of a [[pd series]] or a [[pd dataframe]] with the values of another but only then [[pd index]] (and [[pd column]]) are matching 
- if `overwrite=False` is set only null values are overwritting
- different behavour than the update in a [[py dict]] which is even adding new keys if not present in dict1


## [[pd update]] unsave behavour
- when updating a [[pd slicing|slice]] with different data type it does not work because of the [[pd view and copy behavour]] of [[pandas]]

#### [[pd view and copy behavour]]

- When a slice of a [[pd dataframe]] or [[pd series]] is defined, it's a view of the data of the original object
- when the data is changed to values of the same data type both objects are changed
- when values of the silce or the original objects are changed to a different data type the underlaying data is copied, and both objects have their own data from now on
- to force a copy use [[pd dataframe]]`.copy()`

## example

```python
series1 = pd.Series({
	"A": 1,
	"B": 2,
	"C": 3,
	"D": 4,
})
```

#### on a slice with an update that is changing the data type [[pd update]] has no effect

```python
series1["A":"C"].update({"A": 77.7})
# A 1 
# B 2 
# C 3 
# D 4 
# E 5
```

#### on a slice with an updatewithout data type change [[pd update]] works

```python
series1["A":"C"].update({"A": 77})
# A 77 
# B 2 
# C 3 
# D 4 
# E 5
```


#### on a non sliced object up, update allways works

```python
series1.update({"A": 77})
# A 77.7 
# B 2 
# C 3 
# D 4 
# E 5
```

#### how to make it save

```python
series1_splice = series1["A":"C"].copy()
series1_splice.update({"A": 77.7})
series1["A":"C"] = series1_splice
# A 77.7 
# B 2 
# C 3 
# D 4 
# E 5
```

Tags: code pandas
<!--ID: 1698489556146-->
END