## Problem 49
***Asked by Amazon.***
### Task
**Given an array of numbers, find the maximum sum of any contiguous subarray of the array.**
***Do this in O(N) time.***
### Sample Input
**34 -50 42 14 -5 86**
### Sample Output
**137**
### Explanation
**Maximum sum would be 137 (= 42 + 14 + (-5) + 86).**
### Sample Input
**-5 -1 -8 -9**
### Sample Output
**0**
### Explanation
**Maximum sum would be 0 (can't take any elements).**

### Approach 1
**:stopwatch: Time Complexity - O(n<sup>2</sup>).**
**:floppy_disk: Space Complexity - O(n).**

### Solution | Python
```python
size = int(input())
x = [int(n) for n in input().split()]

p = 0                       
for i in range(size):     
  s = 0                     
  for j in range(i, size):
    s += x[j]               
    p = max(p, s)           
                            
print(p) 
```

### Solution | C++
```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
  vector<int> x;
  int size, p=0, s=0, n;
  cin>>size;
  for (int i=0; i<size; i++) {
    cin>>n;
    x.push_back(n);
  }
  
  for (int i=0; i<size; i++) {
    s = 0;
    for (int j=i; j<size; j++) {
      s += x[j];
      p = max(p, s);
    }
  }

  cout<<p;
  return 0;
}
```

### Approach 2
**:stopwatch: Time Complexity - O(n).**
**:floppy_disk: Space Complexity - O(n).**

### Solution | Python
```python
size = int(input())
x = [int(x) for x in input().split()]

s = 0                  
p = 0                  
for k in range(size):
  s = max(x[k], s+x[k])
  p = max(p, s)        
                       
print(p)  
```

### Solution | C++
```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
  vector<int> x;
  int size, p=0, s=0, n;
  cin>>size;
  for (int i=0; i<size; i++) {
    cin>>n;
    x.push_back(n);
  }
  
  for (int i=0; i<size; i++) {
    s = max(x[i], s+x[i]);
    p = max(p, s);
  }

  cout<<p;
  return 0;
}
```

|**:file_folder: [INDEX](https://github.com/theInvincible/Daily-Coding-Problem/blob/master/Collection/INDEX.md)**|
|----------------------------------------------------------------------------------------------------------------|
