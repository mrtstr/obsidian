[[polars]]
[[pa ListArray]]


```python
offset = pa.array([0,2,4,6])
array = pa.array([1,2,3,4,5,6])
l = pa.ListArray.from_arrays(
	offset,
	array,
)
```
| | 0 | 
|---:|:------| 
| 0 | [1 2] | 
| 1 | [3 4] | 
| 2 | [5 6] |

```python
def concat_pa_ListArray(list_arrays_to_concat):
	return pl.Series(list_arrays_to_concat[0]).arr.concat(
		[
			pl.Series(list_array)
			for list_array in list_arrays_to_concat[1:]
		]
	)
concat_pa_ListArray([l, l])
```


| | 0 | 
|---:|:------| 
| 0 | [1 2 1 2] | 
| 1 | [3 4 3 4] | 
| 2 | [5 6 5 6] |

# anki

START
Basic
[[pa ListArray]] use case:
- concat two [[pa ListArray]] using [[polars]]
- concat `[l, l]`
```python
offset = pa.array([0,2,4,6])
array = pa.array([1,2,3,4,5,6])
l = pa.ListArray.from_arrays(
	offset,
	array,
)
```
| | 0 | 
|---:|:------| 
| 0 | [1 2] | 
| 1 | [3 4] | 
| 2 | [5 6] |

Back: 
```python
def concat_pa_ListArray(list_arrays_to_concat):
	return pl.Series(list_arrays_to_concat[0]).arr.concat(
		[
			pl.Series(list_array)
			for list_array in list_arrays_to_concat[1:]
		]
	)
concat_pa_ListArray([l, l])
```


| | 0 | 
|---:|:------| 
| 0 | [1 2 1 2] | 
| 1 | [3 4 3 4] | 
| 2 | [5 6 5 6] |

Tags: code pyarrow
<!--ID: 1682157860034-->
END