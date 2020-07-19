## Problem 35
***Asked by Google.***
### Task
**Given an array of strictly the characters 'R', 'G', and 'B', segregate the values of the array so that all the Rs come first, the Gs come second and the Bs come last.**  
**You can only swap elements of the array.**  

>**First line of input contains size of the array.**  
>**Second line of input contains elements of array seperated by space.**
### Sample Input
**G B R R B R G**
### Sample Output
**R R R G G B B**

### Approach
>**Take character 'G' as a pivot.**  
>**Traverse through the array and compare each character with pivot i.e. 'G'.**  
>>**If character is 'R', place it at left side of 'G'.**  
>>**If character is 'B', place it at right side of 'G'.**  

**:stopwatch:Time Complexity - O(n).**  
**:floppy_disk:Space Complexity - O(1).** 

### Solution | Python
```python
size = int(input())
array = input().split() 
red, green, blue = 0, 0, size - 1

while green <= blue:
    if array[green] == 'R':
        array[green], array[red] = array[red], array[green] 
        red += 1
        green += 1
    elif array[green] == 'G':
        green += 1
    else:
        array[green], array[blue] = array[blue], array[green]
        blue -= 1

print(array)
```
### Solution | C++
```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
  vector<char> arr;
  int size = 7, red=0, green=0, blue;
  char c;
  cin>>size;
  blue = size - 1;
  for (int i=0; i<size; i++) {
    cin>>c;
    arr.push_back(c);
  }
  while (green <= blue) {
    if (arr[green] == 'R') {
        swap(arr[green], arr[red]);
        red++;
        green++;
    }
    else if (arr[green] == 'G')
        green++;
    else {
        swap(arr[blue], arr[green]);
        blue--;
    }
  }
  for (auto i: arr)
    cout<<i<<" ";
  
  return 0;
}
```

### Reference
**:arrow_forward: [Youtube](https://youtu.be/LP6doGhSZ3M)**

|**:house: [HOME](https://github.com/theInvincible/Daily-Coding-Problem/)**|
|--------------------------------------------------------------------------|
