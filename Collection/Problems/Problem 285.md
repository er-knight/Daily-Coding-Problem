Asked by Mailchimp.

You are given an array representing the heights of neighboring buildings on a city street, from east to west. The city assessor would like you to write an algorithm that returns how many of these buildings have a view of the setting sun, in order to properly value the street.

For example, given the array `[3, 7, 8, 3, 6, 1]`, you should return `3`, since the top floors of the buildings with heights `8`, `6`, and `1` all have an unobstructed view to the west.

Can you do this using just one forward pass through the array?

<details>
<summary>Python</summary>

```python
def sun_view(a):
    # last building always have view of setting sun
    c = 1 
    m = a[-1]
    for i in range(len(a)-2, -1, -1):
        if (a[i] > m):
            c += 1
            m = a[i]
    return c
    
if __name__ == '__main__':
    
    a = [3, 7, 8, 3, 6, 1]
    
    print(sun_view(a)) # 3
    
    a = [9, 2, 8, 4, 7]
    
    print(sun_view(a)) # 3
```
</details>

<details>
<summary>C++</summary>
    
```cpp
#include <iostream>
#include <vector>
using namespace std;

int sun_view(vector<int>& a) {
    // last building always have view of setting sun
    int c = 1, m = a[a.size()-1];
    
    for (int i=a.size()-2; i >= 0; i--) {
        if (a[i] > m) {
            c++;
            m = a[i];
        }
    }
    return c;
}
    
int main() {
    vector<int> a = {3, 7, 8, 3, 6, 1};
    
    cout << sun_view(a) << endl; // 3
    
    a = {9, 2, 8, 4, 7};
    
    cout << sun_view(a) << endl; // 3
    
    return 0;
}
```
</details>
