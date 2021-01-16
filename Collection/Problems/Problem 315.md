Asked by Google.

In linear algebra, a Toeplitz matrix is one in which the elements on any given diagonal from top left to bottom right are identical.

Here is an example:
```
1 2 3 4 8
5 1 2 3 4
4 5 1 2 3
7 4 5 1 2
```
Write a program to determine whether a given input is a Toeplitz matrix.

<details>
<summary>Python</summary>

```python
def is_toeplitz(m):
    for i in range(1, len(m)):
        for j in range(1, len(m[i])):
            if (m[i][j] != m[i-1][j-1]):
                return False
                
    return True
        
if __name__ == '__main__':
    m = [[1, 2, 3, 4, 8],
         [5, 1, 2, 3, 4],
         [4, 5, 1, 2, 3],
         [7, 4, 5, 1, 2]]
         
    print(is_toeplitz(m))
    
    m = [[1, 2, 3, 4, 8],
         [5, 1, 2, 3, 4],
         [4, 5, 0, 2, 3],
         [7, 4, 5, 1, 2]]
         
    print(is_toeplitz(m))
```
</details>

<details>
<summary>C++</summary>

```cpp
#include <iostream>
#include <vector>
using namespace std;

bool is_toeplitz(vector<vector<int>>& m) {
    for (int i=1; i < m.size(); i++) {
        for (int j=1; j < m[i].size(); j++) {
            if (m[i][j] != m[i-1][j-1]) {
                return false;
            }
        }
    }
    
    return true;
}

int main() {
    vector<vector<int>> m = {{1, 2, 3, 4, 8},
                             {5, 1, 2, 3, 4},
                             {4, 5, 1, 2, 3},
                             {7, 4, 5, 1, 2}};
                             
    cout << (is_toeplitz(m) ? "True" : "False") << endl;
    
    m = {{1, 2, 3, 4, 8},
         {5, 1, 2, 3, 4},
         {4, 5, 0, 2, 3},
         {7, 4, 5, 1, 2}};
                             
    cout << (is_toeplitz(m) ? "True" : "False") << endl;
    
    return 0;
}
```
</details>
