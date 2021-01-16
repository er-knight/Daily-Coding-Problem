Asked by Facebook.

Given an integer `n`, find the next biggest integer with the same number of 1-bits on.  
For example, given the number `6` (`0110` in binary), return `9` (`1001`).

<details>
<summary>Python</summary>

```python
def set_bits(n):
    c = 0 # count of set bits
    while (n):
        n &= (n-1)
        c += 1
        
    return c
    
def next_int(n):
    c = set_bits(n) # count of set bits in n
    
    n += 1
    while True:
        if (set_bits(n) == c):
            return n
        n += 1
        
if __name__ == '__main__':
    
    n = 6
    print(next_int(n))
```
</details>

<details>
<summary>C++</summary>

```cpp
#include <iostream>
using namespace std;

int set_bits(int n) {
    int c = 0; // count of set bits
    while (n) {
        n &= (n-1);
        c++;
    }    
    return c;
}
    
int next_int(int n) {
    int c = set_bits(n); // count of set bits in n
    
    n++;
    while (true) {
        if (set_bits(n) == c)
            return n;
        n++;
    }
}

int main() {
    int n = 6;
    cout << next_int(n) << endl;
    return 0;
}
```
</details>
