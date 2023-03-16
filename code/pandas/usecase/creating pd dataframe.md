## creating a [[pd DataFrame]]
### from 2D [[np array]]
- takes the data from the array but column names and [[pd Index]] have to be provided
### from nested structures 
- (1D arrays, lists, dicts, series) of 1D arrays, lists, dicts, series
- in case of unlabelled structures (arrays, lists) a column name and [[pd Index]] can be provided
```python
d = {
    "one": pd.Series([1.0, 2.0, 3.0], index=["a", "b", "c"]),
    "two": pd.Series([1.0, 2.0, 3.0, 4.0], index=["a", "b", "c", "d"]),
df = pd.DataFrame(d)
}
#    one  two
# a  1.0  1.0
# b  2.0  2.0
# c  3.0  3.0
# d  NaN  4.0
```
### from another [[pd DataFrame]]
creating a changed version of another [[pd DataFrame]]
- as a subset of a [[pd DataFrame]] ([[pd Index]], columns)
- as a filled up version
- rearranging [[pd Index]] and columns
```python
pd.DataFrame(d, index=["d", "b", "a"], columns=["one", "two", "three"])
#    one  two  three
# d  NaN  4.0  NaN
# b  2.0  2.0  NaN
# a  1.0  1.0  NaN
```


# anki

START
Basic
pandas dataframe: how to create it (3 with code examples)
Back: 
## creating a [[pd DataFrame]]
### from 2D [[np array]]
- takes the data from the array but column names and [[pd Index]] have to be provided
### from nested structures 
- (1D arrays, lists, dicts, series) of 1D arrays, lists, dicts, series
- in case of unlabelled structures (arrays, lists) a column name and [[pd Index]] can be provided
```python
d = {
    "one": pd.Series([1.0, 2.0, 3.0], index=["a", "b", "c"]),
    "two": pd.Series([1.0, 2.0, 3.0, 4.0], index=["a", "b", "c", "d"]),
df = pd.DataFrame(d)
}
#    one  two
# a  1.0  1.0
# b  2.0  2.0
# c  3.0  3.0
# d  NaN  4.0
```
### from another [[pd DataFrame]]
creating a changed version of another [[pd DataFrame]]
- as a subset of a [[pd DataFrame]] ([[pd Index]], columns)
- as a filled up version
- rearranging [[pd Index]] and columns
```python
pd.DataFrame(d, index=["d", "b", "a"], columns=["one", "two", "three"])
#    one  two  three
# d  NaN  4.0  NaN
# b  2.0  2.0  NaN
# a  1.0  1.0  NaN
```
Tags: code, pandas
<!--ID: 1667921722411-->
END