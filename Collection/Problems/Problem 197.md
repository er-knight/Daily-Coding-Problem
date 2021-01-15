Asked by Amazon.

<kbd>array</kbd>

Given an array `a` and a number `k` that's smaller than the length of the array, rotate `a` to the right by `k` elements in-place.

<details>
  <summary>Input</summary>
  
  ```
  a = [2, 3, 1, 6, 4, 8]
  k = 2
  ```
</details>

<details>
  <summary>Output</summary>
  
  ```
  4 8 2 3 1 6
  ```
</details>

<details>
  <summary>Python</summary>
  
```python
a = [2, 3, 1, 6, 4, 8]

k = 2 

k = len(a) - k # comment this line to rotate left

while (k > 0):
    for i in range(len(a)-1):
        a[i], a[i+1] = a[i+1], a[i]
    k -= 1
    
print(*a, sep=' ')
```
</details>

<details>
  <summary>C++</summary>

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
    vector<int> a = {2, 3, 1, 6, 4, 8};

    int k = 2;
    
    k = a.size() - k; // comment this line to rotate left
    
    while (k--) {
        for (int i=0; i < a.size()-1; i++) {
            swap(a[i], a[i+1]);
        }
    } 
    for (int i : a) {
        cout << i << " ";
    }
}
```
</details>
