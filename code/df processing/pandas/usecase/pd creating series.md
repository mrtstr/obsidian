## creating a pandas series
### from [[np array]] / [[py list|python list]]
```python
pd.Series([1,2,3,4], index = ["a", "b", "c", "d"])
# a 1 
# b 2 
# c 3 
# d 4 
```
- if no index is provided, the index will be the element count
### from [[py dict|python dict]]
```python
pd.Series({
"a": 1,
"b": 2,
"c": 3,
"d": 4,
# a 1 
# b 2 
# c 3 
# d 4 
})
```
- the keys will be the index and the values the data
### from constant
```python
pd.Series(5.0, index = ["a", "b", "c", "d"])
# a 5.0 
# b 5.0 
# c 5.0 
# d 5.0 
```

# anki

START
Basic
pandas series: how to create it (3 with examples)
Back: 

## creating a pandas series
### from [[np array]] / [[py list|python list]]
```python
pd.Series([1,2,3,4], index = ["a", "b", "c", "d"])
# a 1 
# b 2 
# c 3 
# d 4 
```
- if no index is provided, the index will be the element count
### from [[py dict|python dict]]
```python
pd.Series({
"a": 1,
"b": 2,
"c": 3,
"d": 4,
# a 1 
# b 2 
# c 3 
# d 4 
})
```
- the keys will be the index and the values the data
### from constant
```python
pd.Series(5.0, index = ["a", "b", "c", "d"])
# a 5.0 
# b 5.0 
# c 5.0 
# d 5.0 
```
Tags: code, pandas
<!--ID: 1667921722413-->
END