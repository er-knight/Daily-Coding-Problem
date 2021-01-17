Asked by Apple.

A fixed point in an array is an element whose value is equal to its index. Given a sorted array of distinct elements, return a fixed point, if one exists. Otherwise, return False.

For example, given `[-6, 0, 2, 40]`, you should return `2`. Given `[1, 5, 7, 8]`, you should return `False`.

<details>
<summary>Python</summary>

```python
def fixed_point(a):
    for i in range(len(a)):
        if (a[i] == i):
            return i
            
    return -1
    
if __name__ == '__main__':
    
    a = [-6, 0, 2, 40]
    
    p = fixed_point(a)
    
    print('False' if (p == -1) else p)
    
    a = [1, 5, 7, 8]
    
    p = fixed_point(a)
    
    print('False' if (p == -1) else p)
```
</details>

<details>
<summary>C++</summary>

```cpp
#include <iostream>
#include <vector>
using namespace std;

int fixed_point(vector<int>& a) {
    for (int i=0; i < a.size(); i++) {
        if (a[i] == i) {
            return i;
        }
    }
    return -1;
}

int main() {
    vector<int> a = {-6, 0, 2, 40};
    
    int p = fixed_point(a);
    
    if (p == -1) cout << "False" << endl; else cout << p << endl;
    
    a = {1, 5, 7, 8};
    
    p = fixed_point(a);
    
    if (p == -1) cout << "False" << endl; else cout << p << endl;
    
    return 0;
}
```
</details>
