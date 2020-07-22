## Problem 4
***Asked by Stripe.***
### Task
**Given an array of integers, find the first missing positive integer in linear time and constant space. In other words, find the lowest positive integer that does not exist in the array. The array can contain duplicates and negative numbers as well.**  
***Note: You can modify the input array in-place.***

>**First line of input contains size of the array.**  
>**Second line of input contains elements of the array seperated by space.**
### Sample Input
**4**  
**3 4 -1 1**
### Sample Output
**2**
### Explanation
**2 is the smallest positive integer not present in the array.**
### Sample Input
**3**  
**1 2 0**
### Sample Output
**3**
### Explanation
**3 is the smallest positive integer not present in the array.**
### Approach
> **Find MAX element of the array.**  
> **Iterate through integers from 1 to MAX of array, check for every integer if it is present in the array.**
>> **If any integer is not present, then print that element and break the loop.**  
>> **Else print MAX + 1.**

**:stopwatch: Time Complexity - O(n).**    
**:floppy_disk: Space Complexity - O(1).**
### Code (Python)
```python
size = int(input())
array = [int(x) for x in input().split()]

for i in range(1, max(array) + 1):
  if i not in array:
    print(i)
    break
  elif i == max(array):
    print(max + 1)
```
### Code (C++)
```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
  vector<int> arr;
  int size, n;
  cin>>size;
  for (int i=0; i<size; i++) {
    cin>>n;
    arr.push_back(n);
  }  
  int m = *max_element(arr.begin(), arr.end()); //returns an iterator pointing to maximum element
  for (int i=1; i<=m ; i++) {
    if (find(arr.begin(), arr.end(), i) == arr.end()) {
      cout<<i;
      break;
    }
    else if(i == m)
      cout<<m+1;
  }
  return 0;
}
```

|**:file_folder: [INDEX](https://github.com/theInvincible/Daily-Coding-Problem/blob/master/Collection/INDEX.md)**|
|----------------------------------------------------------------------------------------------------------------|
