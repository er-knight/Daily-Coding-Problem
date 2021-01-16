Asked by Salesforce.

Given an array of integers, find the maximum XOR of any two elements.

<details>
<summary>Python</summary>

```python
def max_xor(a):
    max_ = 0
    
    for i in range(len(a)):
        for j in range(i+1, len(a)):
            max_ = max(max_, a[i] ^ a[j])

    return max_
    
if __name__ == "__main__":
    
    a = [1, 2, 3, 4, 5]
    print(max_xor(a))
```
</details>

<details>
<summary>C++</summary>

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int max_xor(vector<int>& a) {
    int max_ = 0;
    
    for (int i=0; i < a.size(); i++) {
        for (int j=i+1; j < a.size(); j++) {
            max_ = max(max_, a[i] ^ a[j]);
        }
    }
    
    return max_;
}    
    
int main() {
    vector<int> a = {1, 2, 3, 4, 5};
    
    cout << max_xor(a) << endl;
    return 0;
}
```
</details>
