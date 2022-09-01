### solve the two sum problem ([[arithmetic sum problems]]) with a [[sliding window]]

#### problem
- given a list of integers: 
- find the indices of the two numbers that are equal to a given target when summed up. 
- the list is sorted
-

#### [[sliding window]] solution
(in $O(nlog(n))$ time and  $O(1)$ space)
- sort the list
- use a left and a right pointer, with init state at start and end of list
- of sum is bigger than taget: decrement the right pointer (only way to decrease sum)
- of sum is smaller than the taget: increment the left pointer (only way to increase sum)
→ will always find a solution when it exists 

```python
def twoSum( numbers: List[int], target: int) -> List[int]:
	min_pointer = 0
	end_pointer = len(numbers) - 1
	while True:
		sum_ = numbers[min_pointer] + numbers[end_pointer]
		if sum_ == target:
			return [min_pointer+1, end_pointer+1]
		if sum_ > target:
			end_pointer = end_pointer - 1
		else:
			min_pointer = min_pointer + 1

```

#### [[hash map]] solution
(in $O(n)$ time and  $O(n)$ space)
hash-map approach: save rest in hash-map mapped to the index
```python
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        rest = dict()
        for index, num in enumerate(nums):
            rest[target - num] = index
        for index, num in enumerate(nums):
            if num in rest.keys():
                if rest[num] != index:
                    return [rest[num], index]
```

START
Basic
- given a list of integers: 
- find the indices of the two numbers that are equal to a given target when summed up. 
- the list is sorted
- in $O(n)$ time and  $O(1)$ space
Back: 
```python
def twoSum( numbers: List[int], target: int) -> List[int]:
	min_pointer = 0
	end_pointer = len(numbers) - 1
	while True:
		sum_ = numbers[min_pointer] + numbers[end_pointer]
		if sum_ == target:
			return [min_pointer+1, end_pointer+1]
		if sum_ > target:
			end_pointer = end_pointer - 1
		else:
			min_pointer = min_pointer + 1

```
Tags: algorithms, problem
<!--ID: 1661978397120-->
END



START
Basic
- given a list of integers: 
- find the indices of the two numbers that are equal to a given target when summed up. 
- in $O(n)$ time
Back: 
```python
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        rest = dict()
        for index, num in enumerate(nums):
            rest[target - num] = index
        for index, num in enumerate(nums):
            if num in rest.keys():
                if rest[num] != index:
                    return [rest[num], index]
```

Tags: algorithms, problem
<!--ID: 1661978397116-->
END
