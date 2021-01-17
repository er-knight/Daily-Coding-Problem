Asked by Stripe.

Given an integer `n`, return the length of the longest consecutive run of 1s in its binary representation.

For example, given `156`, you should return `3`.

<details>
<summary>Python</summary>

```python
def longest_ones(n):
    c = 0 # count
    t = 0 # temporary count
    while (n):
        if (n % 2 == 0):
            t = 0
        else:
            t += 1
        n //= 2
        c = max(t, c)
            
    return c
    
if __name__ == '__main__':
    
    print(longest_ones(61)) # 4
    
    print(longest_ones(156)) # 3
```
</details>

<details>
<summary>C++</summary>

```cpp
#include <iostream>
#include <algorithm>
using namespace std;

int longest_ones(int n) {
    int c = 0, t = 0;
    while (n) {
        if (n % 2 == 0) {
            t = 0;
        }
        else {
            t += 1;
        }
        n /= 2;
        c = max(t, c);
    } 
           
    return c;
}

int main() {
    cout << longest_ones(61) << endl; // 4
    
    cout << longest_ones(156) << endl; // 3
    
    return 0;
}
```
</details>
