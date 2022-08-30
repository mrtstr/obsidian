## Example
Finding the longest sequence in string

```python
    def lengthOfLongestSubstring(self, s: str) -> int:
        char_set = set()
        max_substring_len = 0
        left_pointer = 0
        for right_pointer in range(len(s)):
            while s[right_pointer] in char_set:
                char_set.remove(s[left_pointer])
                left_pointer = left_pointer + 1
            char_set.add(s[right_pointer])
            if max_substring_len < len(char_set):
                max_substring_len = len(char_set)
        return max_substring_len

```


START
Basic
Finding the longest sequence in string in $O(n)$.
Back: 
```python
def lengthOfLongestSubstring(self, s: str) -> int:
	char_set = set()
	max_substring_len = 0
	left_pointer = 0
	for right_pointer in range(len(s)):
		while s[right_pointer] in char_set:
			char_set.remove(s[left_pointer])
			left_pointer = left_pointer + 1
		char_set.add(s[right_pointer])
		if max_substring_len < len(char_set):
			max_substring_len = len(char_set)
	return max_substring_len

```
Tags: algorithms, leetcode
<!--ID: 1661890306173-->
END