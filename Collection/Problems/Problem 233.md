Asked by Apple.

Implement the function `fib(n)`, which returns the n<sup>th</sup> number in the [Fibonacci sequence](https://en.wikipedia.org/wiki/Fibonacci_number), using only `O(1)` space.

<details>
<summary>Python</summary>

```python
def fib(n):
    a, b = 0, 1

    for i in range(n):
        a, b = b, (a + b)
        
    return a
        
if __name__ == '__main__':
    
    print(fib(8))  # 21
    
    print(fib(11)) # 89
```
</details>

<details>
<summary>C++</summary>

```cpp
#include <iostream>
using namespace std;

int fib(int n) {
    int a = 0, b = 1, t;
    
    for (int i=0; i < n; i++) {
        t = a;
        a = b;
        b = (t + b);
    }
    
    return a;
}
        
int main() {
    cout << fib(8) << endl;  // 21
    cout << fib(11) << endl; // 89
    return 0;
}
```
</details>
