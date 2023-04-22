## ListArray
- [[pa Array]] containing [[pa ListType]]
- data is saved in a nomal (flat) [[pa Array]] with an additional [[pa Array]] named `offsets` containing the positions where one list ands and another begins
```python
list_array = pa.array([[1,2,3], [4,5,6]])
list_array.type
# ListType(list<item: int64>)
list_array.offsets
# [ 0, 3, 6 ]
list_array
list_array.flatten()
```

| | 0 | 
|---:|:--------| 
| 0 | [1 2 3] | 
| 1 | [4 5 6] | 

| | 0 | 
|---:|----:| 
| 0 | 1 | 
| 1 | 2 | 
| 2 | 3 | 
| 3 | 4 | 
| 4 | 5 | 
| 5 | 6 |

```python
offset = pa.array([0,2,4,6])
array = pa.array([1,2,3,4,5,6])
pa.ListArray.from_arrays(
	offset,
	array,
)
# equivalent to the following
pa.FixedSizeListArray.from_arrays(array, 2)
```

| | 0 | 
|---:|:------| 
| 0 | [1 2] | 
| 1 | [3 4] | 
| 2 | [5 6] |


# anki

START
Basic
[[pa ListArray]]
- concept
- memory representation
- example 
	- create it from a nested python list
	- flatten it
	- create it from a flat [[pa Array]] with varring list length
	- create it from a flat [[pa Array]] with fixed list length

Back: 
- [[pa Array]] containing [[pa ListType]]
- data is saved in a nomal (flat) [[pa Array]] with an additional [[pa Array]] named `offsets` containing the positions where one list ands and another begins
```python
list_array = pa.array([[1,2,3], [4,5,6]])
list_array.type
# ListType(list<item: int64>)
list_array.offsets
# [ 0, 3, 6 ]
list_array
list_array.flatten()
```

| | 0 | 
|---:|:--------| 
| 0 | [1 2 3] | 
| 1 | [4 5 6] | 

| | 0 | 
|---:|----:| 
| 0 | 1 | 
| 1 | 2 | 
| 2 | 3 | 
| 3 | 4 | 
| 4 | 5 | 
| 5 | 6 |

```python
offset = pa.array([0,2,4,6])
array = pa.array([1,2,3,4,5,6])
pa.ListArray.from_arrays(
	offset,
	array,
)
# equivalent to the following
pa.FixedSizeListArray.from_arrays(array, 2)
```

| | 0 | 
|---:|:------| 
| 0 | [1 2] | 
| 1 | [3 4] | 
| 2 | [5 6] |

Tags: code pyarrow
<!--ID: 1682157860043-->
END