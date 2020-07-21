## Problem 70
***Asked by Microsoft.***
### Task
**A number is considered perfect if its digits sum up to exactly 10.**
**Given a positive integer** ***n*** **(** ***n*** **>0), return the n<sup>th</sup> perfect number.**

>**First and only line of input contains an integer n.**

### Sample Input
**10**
### Sample Output
**109**
### Sample Input
**20**
### Sample Output
**208**

### Approach
>**Starting from num = 19 (which is 1<sup>st</sup> perfect number), increment num by 9.**
>**If sum of digits of resulting number is 10, then increase count.**
>**Repeat the above process untill count becomes equal to** ***n.***

### Solution | Python
```python
n = int(input())
count = 1
num = 19

while (True):
  if n == 1:
    print(num)
    break

  num += 9
  if sum([int(x) for x in str(num)]) == 10:
    count += 1
  
  if count == n:
    print(num)
    break
```
### Solution | C++
```
#include <iostream>
using namespace std;

int main() {
  int n, count=1, num=19, sum;
  cin>>n;
  
  while (true) {
    if (n == 1) {
      cout<<num;
      break;
    }

    num += 9;
    sum = 0;
    for (int x=num; x>0; x /= 10) {
      sum += x%10;
    }
    if (sum == 10)
      count += 1;

    if (count == n) {
      cout<<num;
      break;
    }
  }
  return 0;
}
```

|**:house: [HOME](https://github.com/theInvincible/Daily-Coding-Problem/)**|
|--------------------------------------------------------------------------|
