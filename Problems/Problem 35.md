## Problem 35
***Asked by Google.***
### Task
**Given an array of strictly the characters 'R', 'G', and 'B', segregate the values of the array so that all the Rs come first, the Gs come second and the Bs come last.**  
**You can only swap elements of the array.**  
***Note: Do this in linear time and in-place.***
### Sample Input
**G B R R B R G**
### Sample Output
**R R R G G B B**

### Solution | Python
```python
array = input().split() 
red, green, blue = 0, 0, len(array) - 1

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

**Reference: [Youtube](https://youtu.be/LP6doGhSZ3M)**
