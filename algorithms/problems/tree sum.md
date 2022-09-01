- [[arithmetic sum problems]]
- find triplets of elements with a sum equal to 0 $\in O(n2)$
- no duplicated triplets and don't use an element twice

### solution
- combine [[brute force no repeat, no order]] with a [[sliding window]] approach
- skip indices to prevent duplicates
```python
def threeSum(nums: List[int]) -> List[List[int]]:
	nums=sorted(nums)
	triplets=list()
	for index in range(len(nums)):
		if index != 0 and nums[index - 1] == nums[index]:
			continue
		left_pointer=index + 1
		right_pointer=len(nums) - 1
		while(left_pointer<right_pointer):
			sum_ = nums[left_pointer] + nums[right_pointer] + nums[index]
			if sum_ < 0:
				left_pointer += 1
			elif sum_ > 0:
				right_pointer -= 1
			else:
			if index != right_pointer:
				triplets.append(
					(nums[left_pointer], nums[right_pointer], nums[index])
				)
			while (
				left_pointer < right_pointer 
				and 
				nums[left_pointer] == nums[left_pointer+1]
			):
				left_pointer += 1
			left_pointer += 1
	return triplets
```

