## Problem 61
***Asked by Google.***
### Task
**Implement integer exponentiation. That is, implement the pow(x, y) function, where x and y are integers and returns x<sup>y</sup>.**  
***Note: Do this faster than the naive method of repeated multiplication.***  

>**First and only line of input contains two space seperated integers x and y.**

### Sample Input
**2 10**
### Sample Output
**1024**

### Approach
>**Let** `result = 0`  
>**If power is odd, multiply result with x.**  
>**Update x = x\*x.**  
>**Right shift power by 1.**  
>**Repeat above process untill power becomes 0.**

**:stopwatch: Time Complexity - O(n), where n is the index of most significant bit counting from right.**  
**:floppy_disk: Space Complexity - O(1)**

### Solution | Python
```python
def power(x, y):         
  result = 1           
  power = y 
                                    
  while power:            
    if (power & 1):      
      result *= x
    x *= x            
    power >>= 1   
                         
  return result          
```
```
print(power(2, 10)) 
```

### Solution | C++
```cpp
#include <iostream>
using namespace std;

int power(int x, int y) {
  int result = 1, power = y;

  while (power) {
    if (power & 1)
      result *= x;
    x *= x;
    power >>= 1; 
  }

  return result;
}
```
```
int main() {
  cout<<power(2, 10);
  return 0;
}
```

|**:file_folder: [INDEX](https://github.com/theInvincible/Daily-Coding-Problem/blob/master/Collection/INDEX.md)**|
|----------------------------------------------------------------------------------------------------------------|  
