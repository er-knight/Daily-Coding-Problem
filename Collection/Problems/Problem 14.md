## Problem 14
***Asked by Google.***
### Task
**The area of a circle is defined as πr<sup>2</sup>. Estimate π upto 3 decimal places using [Monte-Carlo method](https://towardsdatascience.com/an-overview-of-monte-carlo-methods-675384eb1694).**

**Hint: The basic equation of a circle is x<sup>2</sup> + y<sup>2</sup> = r<sup>2</sup>.**

### Solution | Python
```python
import random

insideSquare = 0
insideCircle = 0
interval = int(input())

for _ in range(interval):
  x = random.uniform(-1.000, 1.000)
  y = random.uniform(-1.000, 1.000)
  insideSquare += 1
  if pow(x, 2) + pow(y, 2) <= 1:
    insideCircle += 1

pi = 4 * (insideCircle/insideSquare)
print(round(pi, 3))
```
```
Input: 100
Output: 3.16

Input: 1000
Output: 3.088

Input: 10000
Output: 3.144
```
### Solution | C++
```cpp
#include <iostream>
#include <random>
using namespace std;

int main() {
  int interval, inside_circle=0, inside_square=0;
  double x, y;
  default_random_engine generator;
  uniform_real_distribution<double> dis(-1.000, 1.000);
  cin>>interval;  
  for (long int i=0; i<interval; i++) {
    x = dis(generator);
    y = dis(generator);
    inside_square += 1;
    if ((x*x + y*y) <= 1.000) {
      inside_circle += 1;
    }
  }
  printf("%.3f", (4*((float)inside_circle/inside_square)));
  return 0;
}
```
```
Input: 100
Output: 3.240

Input: 1000
Output: 3.168

Input: 10000
Output: 3.179

Input: 100000
Output: 3.146
```
### References
**:green_book: [GeeksforGeeks](https://www.geeksforgeeks.org/estimating-value-pi-using-monte-carlo/)**

|**:house: [HOME](https://github.com/theInvincible/Daily-Coding-Problem/)**|
|--------------------------------------------------------------------------|
