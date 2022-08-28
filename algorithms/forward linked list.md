### Forward linked list
- each node has a value and has a link to the next node
- creating and searching in $\mathcal{O}(n)$ 

### Definition
```python
class ListNode:
	def __init__(self, val=0, next=None):
		self.val = val
		self.next = next
```
### Filling List
```python
my_list = [2,4,3]
l1_start = None
for list_element in my_list:
	if l1_start is None:
		l1_start = ListNode(list_element)
		list_pointer = l1_start
	else:
		list_pointer.next = ListNode(list_element)
		list_pointer = list_pointer.next
```

START
Basic
definition of a forward linked list
Back: 
Forward linked list
- each node has a value and has a link to the next node
- creating and searching in $\mathcal{O}(n)$ 

Definition
```python
class ListNode:
	def __init__(self, val=0, next=None):
		self.val = val
		self.next = next
```
Tags: algorithms, leetcode
<!--ID: 1661678999146-->
END

START
Basic
filling of a forward linked list
Back: 
```python
my_list = [2,4,3]
l1_start = None
for list_element in my_list:
	if l1_start is None:
		l1_start = ListNode(list_element)
		list_pointer = l1_start
	else:
		list_pointer.next = ListNode(list_element)
		list_pointer = list_pointer.next
```
Tags: algorithms, leetcode
<!--ID: 1661678999149-->
END