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
**2**  
**2**
### Explanation
|**Numbers**|**Median**|
|-----------|----------|
|**2**|**median = 2**|      
|**2, 1**|**median = (2 + 1)/2 = 1.5**|   
|**2, 1, 5**|**meadian = 2**|   
|**2, 1, 5, 7**|**median = (2 + 5)/2 = 3.5**    
|**2, 1, 5, 7, 2**|**median = 2**|
|**2, 1, 5, 7, 2, 0**|**median = (2 + 2)/2 = 2.0**|
|**2, 1, 5, 7, 2, 0, 5**|**median = 5**|

### Solution | Python
```python
def median(numList):
  numList.sort()
  if len(numList) % 2 == 0:
    return (numList[len(numList)//2] + numList[len(numList)//2 - 1])/2
  else:
    return numList[len(numList)//2]

size = int(input())
numList = [int(x) for x in input().split()]

for i in range(size):
  print(median(numList[:i+1]))
```

### Solution | C++
```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

float median(vector<int> numList) {
  sort(numList.begin(), numList.end());
  if (numList.size()%2 == 0) 
    return ((float)(numList[numList.size()/2 - 1] + numList[numList.size()/2])/2);
  else
    return (float)numList[numList.size()/2];
}

int main() {
  vector<int> numList;
  int size, x;
  cin>>size;
  for (int i=0; i<size; i++) {
    cin>>x;
    numList.push_back(x); 
    cout<<median(numList)<<"\n";
  }

  return 0;
}
```

|**:house: [HOME](https://github.com/theInvincible/Daily-Coding-Problem/)**|
|--------------------------------------------------------------------------|
