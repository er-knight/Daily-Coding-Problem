Asked by Pivotal.

Write an algorithm that finds the total number of set bits in all integers between `1` and `N` inclusive. 

<details>
<summary>Python</summary>

```python
def set_bits(n):
    c = 0 # count of set bits
    while (n):
        n &= (n-1)
        c += 1
        
    return c
    
if __name__ == '__main__':
    n = 5
    count = 0
    for i in range(1, n+1):
        count += set_bits(i)
        
    print(count)
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
    
int main() {
    int n = 5, count = 0;
    
    for (int i=1; i < n+1; i++) {
        count += set_bits(i);
    }
        
    cout << count << endl;
    return 0;
}
```
</details>
