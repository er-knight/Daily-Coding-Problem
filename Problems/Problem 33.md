## Problem 33
***Asked by Microsoft.***
### Task
**Compute the Running Median of a sequence of numbers. That is, given a stream of numbers, print out the median of the list so far on each new element.**
**Recall that the median of an even-numbered list is the average of the two middle numbers.**

***Note: Numbers must be sorted, before calculating median.***
### Input
**2 1 5 7 2 0 5**
### Output
**2**  
**1.5**  
**2**  
**3.5**  
**2**  
**2.0**  
**2**
### Explanation
|**Numbers**|**Median**|
|-----------|----------|
|**2**|**median = 2**|      
|**2, 1**|**median = (2 + 1)/2 = 1.5**|   
|**2, 1, 5**|**meadian = 2**|   
|**2, 1, 5, 7**|**median = (2 + 5)/2 = 3.5**    
|**2, 1, 5, 7, 2,**|**median = 2**|
|**2, 1, 5, 7, 2, 0,**|**median = (2 + 2)/2 = 2.0**|
|**2, 1, 5, 7, 2, 0, 5,**|**median = 5**|

|**:house: [HOME](https://github.com/theInvincible/Daily-Coding-Problem/)**|
|--------------------------------------------------------------------------|
