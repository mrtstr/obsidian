# example series
```python
pd_df1 = pd.DataFrame(
	{"a": 1, "b":2, "c":3, "d":4},
)
  
# a   1 
# b   2  
# c   3 
# d   4 
```
# Series
- one dimensional labeled array
- labels of the axis is called index
- has a single dtype and often uses [[np dtypes]] 
- has a name attribute
- similar to a column of a [[pd dataframe]]

## array like properties
- behaves similar to [[np array]] (most [[numpy]] functions can use it)
- [[pd series|Series]].array containing the array like data as ExtensionArray
- ExtensionArray is a wrapper round a 1d array
- [[pd series|Series]].to_numpy() return the actual [[np array]]

## dict like properties
- a [[pd series|Series]] behaves like a [[py dict]]
```python
s.get("f", None)
# returns object or None if the key is not in the index
s["f"]
# returns object or raises error key not in the index
```
## Vectorised operations
- behaves like [[np array]] with the difference that it aligns the elements by the index when doing operations between series 
- the result is NaN when one element has not matching [[pd index]] in the other [[pd series|Series]].
- The [[pd index|index]] of the results of an operation between [[pd series|Series]] is the [[pd index|index]] [[union]] of the [[pd index|indices]] of the operands but only elements with an [[pd index|index]] inside the [[pd index|index]] [[intersection of sets]] of have values (the rest is Nan)
```python
# operation between series
s + s
# operation between series and constants
s * 2
# as input for np operations
np.exp(s)
```
# Anki

START
Basic
pandas series: behaviour in a vectorised operation
Back: 
## Vectorised operations
- behaves like [[np array]] with the difference that it aligns the elements by the index when doing operations between series 
- the result is NaN when one element has not matching [[pd index]] in the other [[pd series|Series]].
- The [[pd index|index]] of the results of an operation between [[pd series|Series]] is the [[pd index|index]] [[union]] of the [[pd index|indices]] of the operands but only elements with an [[pd index|index]] inside the [[pd index|index]] [[intersection of sets]] of have values (the rest is Nan)
```python
# operation between series
s + s
# operation between series and constants
s * 2
# as input for np operations
np.exp(s)
```
Tags: code pandas
<!--ID: 1667921722436-->
END


START
Basic
pandas series conceptual similarities: array, dict
Back: 
## array like properties
- behaves similar to [[np array]] (most [[numpy]] functions can use it)
- [[pd series|Series]].array containing the array like data as ExtensionArray
- ExtensionArray is a wrapper round a 1d array
- [[pd series|Series]].to_numpy() return the actual [[np array]]

## dict like properties
- a [[pd series|Series]] behaves like a [[py dict]]
```python
s.get("f", None)
# returns object or None if the key is not in the index
s["f"]
# returns object or raises error key not in the index
```
Tags: code pandas
<!--ID: 1667921722438-->
END


START
Basic
pandas series basic concept (6)
Back: 
- one dimensional labeled array
- labels of the axis is called index
- has a single dtype and often uses [[np dtypes]] 
- has a name attribute
- has array and dict like properties
- supports vector operations that align the index

Tags: code pandas
<!--ID: 1667921722440-->
END


START
Basic
```python
series = pd.Series({
"a": 1,
"b": 2,
"c": 3,
"d": 4,
})

print(series[1:] * series[:-1])
```
Back: 
```python
series = pd.Series({
"a": 1,
"b": 2,
"c": 3,
"d": 4,
})

print(series[1:] * series[:-1])
# a NaN 
# b 4.0 
# c 9.0 
# d NaN
```
Tags: code pandas
<!--ID: 1667921722442-->
END