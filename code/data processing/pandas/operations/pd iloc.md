![[pd dataframe#example df]]
selecting columns and rows by position
```python
pd_df1.iloc["<row selection position>", "<column selection by position>"]

pd_df1.iloc[0]
# returns a series containing the first row with index equal to column names

pd_df1.iloc[[0]]
# returns a DataFrame containing only one row 

pd_df1.iloc[:, 0]
# returns a series containing the column with the name "col1"

pd_df1.iloc[:, [0]]
# returns a DataFrame containing with only the column with the name "col1"

pd_df1.iloc[[0, 1], [0, 1]]
# returns a DataFrame that has only the columns col1 and col2 and the rows a and b

pd_df1.iloc[0:1, 0:1]
# returns a DataFrame that has only the columns col1 and col2 and the rows a and b
```

# Anki

START
Basic
pandas DataFrames:
- how to select columns and rows by position
- how to get:
1) slices
2) series
3) single column/row dataframes

Back: 
Using the iloc function:
```python
pd_df1 = pd.DataFrame({
	"col1": {"a": 1, "b":2, "c":3, "d":4},
	"col2": {"a": 5, "b":6, "c":7, "d":8},
	"col3": {"a": 9, "b":10, "c":11, "d":12},
})
  
#  col1 col2 col3
# a   1   5   9
# b   2   6   10
# c   3   7   11
# d   4   8   12
```
```python
pd_df1.iloc["<row selection position>", "<column selection by position>"]

pd_df1.iloc[0]
# returns a series containing the first row with index equal to column names

pd_df1.iloc[[0]]
# returns a DataFrame containing only one row 

pd_df1.iloc[:, 0]
# returns a series containing the column with the name "col1"

pd_df1.iloc[:, [0]]
# returns a DataFrame containing with only the column with the name "col1"

pd_df1.iloc[[0, 1], [0, 1]]
# returns a DataFrame that has only the columns col1 and col2 and the rows a and b

pd_df1.iloc[0:1, 0:1]
# returns a DataFrame that has only the columns col1 and col2 and the rows a and b
```
Tags: code pandas
<!--ID: 1667921722427-->
END