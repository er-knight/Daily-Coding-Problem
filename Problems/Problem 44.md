## Problem 44
***Asked by Google.***
### Task
**We can determine how "Out of Order" an array A is by counting the number of inversions it has. Two elements A[i] and A[j] form an inversion if** `A[i] > A[j]` **but** `i < j` **. That is, a smaller element appears after a larger element.**  
**Given an array, count the number of inversions it has. Do this faster than O(N<sup>2</sup>) time.**
**You may assume each element in the array is distinct.**
### Sample Input
**2 4 1 3 5**
### Sample Output
**3**
### Explanation
**[2, 4, 1, 3, 5] has three inversions: (2, 1), (4, 1), and (4, 3).**
### Sample Input
**5 4 3 2 1**
### Sample Output
**10**
### Explanation
**[5, 4, 3, 2, 1] has ten inversions: every distinct pair forms an inversion.**

### Approach 
>**Apply BUBBLE SORT on the given array.**
>**At each swap of adjacent element, increment the COUNT.**

***Time Complexity - O(n^2) - because of 2 loops.***  
***Space Complexity - O(n) - no extra space is used, except for the array.***

### Code | Python
```
size = int(input())
array = [int(x) for x in input().split()]
inversions = 0

for i in range(len(array)): 
    for j in range(len(array) - i - 1):
        if array[j] > array[j+1]:
            array[j], array[j+1] = array[j+1], array[j]
            inversions += 1

print(inversions)
```
