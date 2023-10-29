## [[pd view and copy behavour]]

- When a slice of a [[pd dataframe]] or [[pd series]] is defined, it's a view of the data of the original object
- when the data is changed to values of the same data type both objects are changed
- when values of the silce or the original objects are changed to a different data type the underlaying data is copied, and both objects have their own data from now on
- to force a copy use [[pd dataframe]]`.copy()`

## example
![[pd dataframe#example df]]

```python
pd_df1_slice = pd_df1.iloc[0:2, 0:3]
pd_df1_slice
```

| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 1 | 5 | 9 | 
| b | 2 | 6 | 10 | 

### both objects share the data
```python
pd_df1.iloc[1,1] = 22
pd_df1_slice.iloc[0,0] = 11

display(pd_df1)
display(pd_df1_slice)
```
 

| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 11 | 5 | 9 | 
| b | 2 | 22 | 10 | 
| c | 3 | 7 | 11 | 
| d | 4 | 8 | 12 |

| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 11 | 5 | 9 | 
| b | 2 | 22 | 10 | 

### the data is copied because the data type changed and a new [[np array]] was created
```python
pd_df1.iloc[1,1] = 22.2
pd_df1_slice.iloc[0,0] = 11.1

display(pd_df1)
display(pd_df1_slice)
```
 

| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 1 | 5 | 9 | 
| b | 2 | 22.2 | 10 | 
| c | 3 | 7 | 11 | 
| d | 4 | 8 | 12 |

| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 11.1 | 5 | 9 | 
| b | 2 | 6 | 10 | 

### the data is copied because the data type changed and a new [[np array]] was created , but only after the first operation was done on the shared data
```python
pd_df1_slice.iloc[0,2] = 99
pd_df1.iloc[1,1] = 22.2
pd_df1_slice.iloc[0,0] = 11.1
pd_df1.iloc[1,2] = 88

display(pd_df1)
display(pd_df1_slice)
```


| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 1 | 5 | 99 | 
| b | 2 | 22.2 | 88 | 
| c | 3 | 7 | 11 | 
| d | 4 | 8 | 12 |

| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 11.1 | 5 | 99 | 
| b | 2 | 6 | 10 | 


# Anki
START
Basic
when does [[pandas]] create a copy and does it create a view when slicing 
- rule with example

Back: 
- When a slice of a [[pd dataframe]] or [[pd series]] is defined, it's a view of the data of the original object
- when the data is changed to values of the same data type both objects are changed
- when values of the silce or the original objects are changed to a different data type the underlaying data is copied, and both objects have their own data from now on
- to force a copy use [[pd dataframe]]`.copy()`

## example

| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 1 | 5 | 9 | 
| b | 2 | 6 | 10 | 
| c | 3 | 7 | 11 | 
| d | 4 | 8 | 12 |

```python
pd_df1_slice = pd_df1.iloc[0:2, 0:3]
pd_df1_slice
```

| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 1 | 5 | 9 | 
| b | 2 | 6 | 10 | 

### both objects share the data
```python
pd_df1.iloc[1,1] = 22
pd_df1_slice.iloc[0,0] = 11

display(pd_df1)
display(pd_df1_slice)
```
 

| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 11 | 5 | 9 | 
| b | 2 | 22 | 10 | 
| c | 3 | 7 | 11 | 
| d | 4 | 8 | 12 |

| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 11 | 5 | 9 | 
| b | 2 | 22 | 10 | 

### the data is copied because the data type changed and a new [[np array]] was created
```python
pd_df1.iloc[1,1] = 22.2
pd_df1_slice.iloc[0,0] = 11.1

display(pd_df1)
display(pd_df1_slice)
```
 

| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 1 | 5 | 9 | 
| b | 2 | 22.2 | 10 | 
| c | 3 | 7 | 11 | 
| d | 4 | 8 | 12 |

| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 11.1 | 5 | 9 | 
| b | 2 | 6 | 10 | 

Tags: code pandas
<!--ID: 1698489556114-->
END


START
Basic
[[pandas]] [[pd view and copy behavour]]: 
- what is the output of the following code
- rule
## example

| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 1 | 5 | 9 | 
| b | 2 | 6 | 10 | 
| c | 3 | 7 | 11 | 
| d | 4 | 8 | 12 |

```python
pd_df1_slice = pd_df1.iloc[0:2, 0:3]
pd_df1_slice
```

| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 1 | 5 | 9 | 
| b | 2 | 6 | 10 | 

```python
pd_df1_slice.iloc[0,2] = 99
pd_df1.iloc[1,1] = 22.2
pd_df1_slice.iloc[0,0] = 11.1
pd_df1.iloc[1,2] = 88

display(pd_df1)
display(pd_df1_slice)
```

Back: 

## rule
- When a slice of a [[pd dataframe]] or [[pd series]] is defined, it's a view of the data of the original object
- when the data is changed to values of the same data type both objects are changed
- when values of the silce or the original objects are changed to a different data type the underlaying data is copied, and both objects have their own data from now on
- to force a copy use [[pd dataframe]]`.copy()`


### the data is copied because the data type changed and a new [[np array]] was created , but only after the first operation was done on the shared data

```python
pd_df1_slice.iloc[0,2] = 99
pd_df1.iloc[1,1] = 22.2
pd_df1_slice.iloc[0,0] = 11.1
pd_df1.iloc[1,2] = 88

display(pd_df1)
display(pd_df1_slice)
```


| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 1 | 5 | 99 | 
| b | 2 | 22.2 | 88 | 
| c | 3 | 7 | 11 | 
| d | 4 | 8 | 12 |

| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 11.1 | 5 | 99 | 
| b | 2 | 6 | 10 | 



Tags: code pandas
<!--ID: 1698489556123-->
END