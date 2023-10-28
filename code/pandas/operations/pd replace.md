- [[pandas]] replace specific values in a [[pd dataframe]] or a [[pd series]] with given values
- replacement values can be given in a [[py dict]]
- the difference to [[pd update]] is that update is a replacement based on [[pd index]] (and [[pd column]]) while replace is a replacement based on value

![[pd dataframe#example df]]

```python
pd_df1.replace(to_replace=1, value=99).to_markdown()
pd_df1.replace(to_replace={6:66, 7: 77}).to_markdown()
```

| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 99 | 5 | 9 | 
| b | 2 | 6 | 10 | 
| c | 3 | 7 | 11 | 
| d | 4 | 8 | 12 |


| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 1 | 5 | 9 | 
| b | 2 | 66 | 10 | 
| c | 3 | 77 | 11 | 
| d | 4 | 8 | 12 |



# Anki

START
Basic
[[pd replace]]
- explainantion
- differnce to [[pd update]]
- examples

| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 1 | 5 | 9 | 
| b | 2 | 6 | 10 | 
| c | 3 | 7 | 11 | 
| d | 4 | 8 | 12 |

```python
pd_df1.replace(to_replace=1, value=99).to_markdown()
pd_df1.replace(to_replace={6:66, 7: 77}).to_markdown()
```

Back: 

- [[pandas]] replace specific values in a [[pd dataframe]] or a [[pd series]] with given values
- replacement values can be given in a [[py dict]]
- the difference to [[pd update]] is that update is a replacement based on [[pd index]] (and [[pd column]]) while replace is a replacement based on value

```python
pd_df1.replace(to_replace=1, value=99).to_markdown()
pd_df1.replace(to_replace={6:66, 7: 77}).to_markdown()
```

| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 99 | 5 | 9 | 
| b | 2 | 6 | 10 | 
| c | 3 | 7 | 11 | 
| d | 4 | 8 | 12 |

| pd_df1 | col1 | col2 | col3 | 
|:---|-------:|-------:|-------:| 
| a | 1 | 5 | 9 | 
| b | 2 | 66 | 10 | 
| c | 3 | 77 | 11 | 
| d | 4 | 8 | 12 |

Tags: code pandas
<!--ID: 1698489556139-->
END

