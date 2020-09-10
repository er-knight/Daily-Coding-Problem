## Problem 30

### Task
**Given an array of non-negative integers that represents a two-dimensional elevation map where each element is unit-width wall and the integer is the height. Suppose it will rain and all spots between two walls get filled up.**   
**Compute how many units of water remain trapped on the map in O(N) time and O(1) space.**  
>**First line of input contains number of elements, n.**  
>**Second line of input contains n space seperated integers which are elements of array.** 

### Sample Input
**3**  
**2 1 2**  
### Sample Output
**1**  
### Explanation
```
 __    __
|__|__|__|
|__|__|__|
 0  1  2
```
**1 unit of water can be stroed at index 1.**

### Sample Input
**6**  
**3 0 1 3 0 5**
### Sample Output
**3**
### Explanation
```
                __
               |__|
 __       __   |__|
|__|     |__|  |__|
|__|   __|__|  |__|
|__|__|__|__|__|__|
 0  1  2  3  4  5
```
**3 units of water can be stored at index 1, 2 unit at index 2 and 3 units at index 4, total 8 units of water can be stored.** 

### Approach: 
- **pre-compute the highest bar on the left and right of every bar in linear time.**
- **Use these pre-computed values to find the amount of water in every array element.**

### Solution | Python
```python
def trappedWater(arr, n): 
    left = [0]*n 
    right = [0]*n 
    water = 0
   
    left[0] = arr[0]
    for i in range(1, n): 
        left[i] = max(left[i-1], arr[i]) 
  
    right[n-1] = arr[n-1] 
    for i in range(n-2, -1, -1): 
        right[i] = max(right[i + 1], arr[i]); 
   
    for i in range(0, n): 
        water += min(left[i], right[i]) - arr[i] 
  
    return water 
  
n = int(input())  
arr = [int(x) for x in input().split()] 
print(findWater(arr, n)) 
```
### Solution | C++
```cpp
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;

int trappedWater(vector<int> arr, int n) {
  int left[n], right[n], water = 0;
  
  left[0] = arr[0]; 
  for (int i = 1; i < n; i++) 
    left[i] = max(left[i - 1], arr[i]); 
    
  right[n - 1] = arr[n - 1]; 
  for (int i = n - 2; i >= 0; i--) 
    right[i] = max(right[i + 1], arr[i]); 
    
  for (int i = 0; i < n; i++) 
    water += min(left[i], right[i]) - arr[i]; 
  
  return water; 
}

int main() { 
    int n, x;
    vector<int> arr;
    cin>>n;
    for(int i=0; i<n; i++) {
      cin>>x;
      arr.push_back(x);
    }
    cout<<trappedWater(arr, n);
    return 0;
}
```
### Reference
**:green_book: [GeeksforGeeks](https://www.geeksforgeeks.org/trapping-rain-water/)**  
**:notebook: [Medium](https://medium.com/@harycane/trapping-rain-water-8a1817b82d98)**

### Practice
**:memo: [LeetCode](https://leetcode.com/problems/trapping-rain-water/)**  
**:memo: [HackerEarth](https://www.hackerearth.com/practice/basic-programming/implementation/basics-of-implementation/practice-problems/algorithm/raeess-liquor-tank/)**

|**:file_folder: [INDEX](https://github.com/theInvincible/Daily-Coding-Problem/blob/master/Collection/INDEX.md)**|
|----------------------------------------------------------------------------------------------------------------|
