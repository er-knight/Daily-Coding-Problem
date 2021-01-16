Asked by Facebook.

Given an array of numbers of length `N`, find both the minimum and maximum using less than `2 * (N - 2)` comparisons.

<details>
<summary>Python</summary>

```python
def min_max(a):
    if len(a) == 1:
        return a[0], a[0]

    if len(a) % 2 == 0: 
        if (a[0] <= a[1]):
            min_ = a[0]
            max_ = a[1]
        else:
            min_ = a[1]
            max_ = a[0]
        s = 2  # start index

    else:
        if (a[0] <= a[1]):
            min_ = a[0]
            max_ = a[1]
        else:
            min_ = a[1]
            max_ = a[0]
        s = 1  # start index
        
    for i in range(s, len(a), 2):
        if a[i] < a[i+1]:
            min_ = min(min_, a[i])
            max_ = max(max_, a[i+1])
        else:
            min_ = min(min_, a[i+1])
            max_ = max(max_, a[i])

        return min_, max_
    
if __name__ == "__main__":
    
    a = [2, 8, 1, 5, 7]
    
    print(*min_max(a), sep=' ')
    
    a = [9, 2, 8, 6, 5, 7]
    
    print(*min_max(a), sep=' ')
```
[stackoverflow.com](https://stackoverflow.com/questions/13544476/how-to-find-max-and-min-in-array-using-minimum-comparisons)
</details>

<details>
<summary>C++</summary>

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
#include <utility>
using namespace std;

pair<int, int> min_max(vector<int>& a) {
    if (a.size() == 1)
        return pair(a[0], a[0]);

    int s, max_, min_;

    if (a.size() % 2 == 0) {
        if (a[0] <= a[1]) {
            min_ = a[0];
            max_ = a[1];
        }
        else {
            min_ = a[1];
            max_ = a[0];
        }
        s = 2;  // start index
    }
    
    else {
        if (a[0] <= a[1]) {
            min_ = a[0];
            max_ = a[1];
        }
        else {
            min_ = a[1];
            max_ = a[0];
        }
        s = 1;  // start index
    }
    for (int i=s; i < a.size(); i += 2) {
        if (a[i] < a[i+1]) {
            min_ = min(min_, a[i]);
            max_ = max(max_, a[i+1]);
        }
        else {
            min_ = min(min_, a[i+1]);
            max_ = max(max_, a[i]);
        }
    }
        
    return pair(min_, max_);
}

int main() {
    vector<int> a = {2, 8, 1, 5, 7};
    
    pair<int, int> answer = min_max(a);
    
    cout << answer.first << " " << answer.second << endl;
    
    a = {9, 2, 8, 6, 5, 7};
    
    answer = min_max(a);
    
    cout << answer.first << " " << answer.second << endl;
    return 0;
}
```
</details>
