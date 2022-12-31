### Problem
- Finding the longest repeat free sequence in string without repeating characters.
-  in $O(n)$

### Solution
- use a [[sliding window]] 

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
Finding the longest repeat free sequence in string without repeating characters in $O(n)$.
Back: 
use a sliding window:
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
Tags: algorithms, problem
<!--ID: 1661890306173-->
END