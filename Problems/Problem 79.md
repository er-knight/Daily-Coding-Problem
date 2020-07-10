## Problem 79
***Asked by Facebook.***
### Task
**Given an array of integers, write a function to determine whether the array could become non-decreasing by modifying at most 1 element.**  

**For example, given the array [10, 5, 7], you should return true, since we can modify the 10 into a 1 to make the array non-decreasing.**  

**Given the array [10, 5, 1], you should return false, since we can't modify any one element to get a non-decreasing array.**

>**Refer Here: [BlogSpot](http://nirajsdatabase.blogspot.com/2017/08/given-array-with-n-integers-your-task.html), [LeetCode Article](https://leetcode.com/articles/non-decreasing-array/), [GitBook1](https://hjweds.gitbooks.io/leetcode/greedy/non-decreasing-array.html), [GitBook2](https://twchen.gitbook.io/leetcode/array/non-decreasing-array)**
>**Practice Here: [LeetCode](https://leetcode.com/problems/non-decreasing-array/)**

```
for i in range(len(array)-1):
  if not (array[i] <= array[i+1]):
    decreaseCount += 1
if decreaseCount > 1:
  return False
else:
  return True
```
```python
# tested at above leetcode problem 311/325 test case passed 
class Solution:
    def checkPossibility(self, nums: List[int]) -> bool:
        count = 0
        for i in range(len(nums)-1):
            if not(nums[i] <= nums[i+1]):
                count += 1
        if count > 1:
            return False
        return True
"""
Input: [3,4,2,3]
Output: true
Expected: false
"""
# here above it given one of wrong output.
```

