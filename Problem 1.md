## Problem 1
***Asked by Google.***

### Task
**Given a list of numbers and a number K, return whether any two numbers from the list add up to K.** 
- **First line of input contains space seperated elements of list.**  
- **Second line of input contains K.**
### Sample Input
**10 15 3 7**  
**17**
### Sample Output
**True**
### Explanation
**10 + 7 = 17. Hence we return True.**
### Sample Input
**10 15 3 7**  
**16**
### Sample Output
**False**
### Explanation
**No any two numbers adds up to 16. Hence we return False.**

### Approach 1: Using 2 loops
- **Try every combination of two numbers from a list and check if they add up to K.** 

***Time Complexity - O(n<sup>2</sup>), where n is length of the list.***  
***Space Complexity - O(1), because extra space is not used.***  
### Code (Python)
```python
def check(myList, K):
    for i in myList:
        for j in myList:
            if (i + j) == K:
                return True
    return False

myList = [int(x) for x in input().split()]
K = int(input())
print(check(myList, K))
```
### Code (C++)
```cpp
```
### Approach 2: Two-Pointers Technique
- **Sort the given list.**  
- **Take two pointers, pointing two start and end of the list, respectively and increase/decrease their value based on the condition.**

***Time Complexity - O(nlogn), where n is length of the list.***  
***Space Complexity - O(1), because extra space is not used.***  
### Code (Python)
```python
```
### Code (C++)
```cpp
```
