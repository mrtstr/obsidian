![[pd dataframe#example df]]


Append a row with ones to pd_df1
```python
append_row = pd.Series([1, 1, 1], index=pd_df1.columns, name="e").to_frame().T
appended_df = pd.concat([pd_df1, append_row])
```

| append_row | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| e | 1 | 1 | 1 |

|appended_df | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 1 | 5 | 9 | 
| b | 2 | 6 | 10 | 
| c | 3 | 7 | 11 | 
| d | 4 | 8 | 12 | 
| e | 1 | 1 | 1 |


# anki

START
Basic
[[pandas]]: append a row with ones to the following [[pd dataframe]]
```python
pd_df1 = pd.DataFrame({
	"col1": {"a": 1, "b":2, "c":3, "d":4},
	"col2": {"a": 5, "b":6, "c":7, "d":8},
	"col3": {"a": 9, "b":10, "c":11, "d":12},
})
```

| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 1 | 5 | 9 | 
| b | 2 | 6 | 10 | 
| c | 3 | 7 | 11 | 
| d | 4 | 8 | 12 |
Back: 
```python
append_row = pd.Series([1, 1, 1], index=pd_df1.columns, name="e").to_frame().T
appended_df = pd.concat([pd_df1, append_row])
```

| append_row | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| e | 1 | 1 | 1 |

|appended_df | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 1 | 5 | 9 | 
| b | 2 | 6 | 10 | 
| c | 3 | 7 | 11 | 
| d | 4 | 8 | 12 | 
| e | 1 | 1 | 1 |

Tags: code pandas
<!--ID: 1678802210291-->
END