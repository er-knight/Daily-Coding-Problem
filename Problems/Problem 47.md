## Problem 47
***Asked by Facebook.***
### Task
**Given a array of numbers representing the stock prices of a company in chronological order, write a function that calculates the maximum profit you could have made from buying and selling that stock once. You must buy before you can sell it.**

>**First line of input contains size of the array**  
>**Second line of input contains prices seperated by space.**  

### Sample Input
**9 11 8 5 7 10**
### Sample Output
**5**
### Explanation
**Buy the stock at 5 dollars and sell it at 10 dollars.**

### Approach 1:
>**Keep track of every possible pair of prices.**

**:stopwatch: Time Complexity - O(n<sup>2</sup>) , because of 2 loops.**  
**:floppy_disk: Space Complexity - O(1).**

### Solution | Python
```python
size = int(input())
array = [int(x) for x in input().split()]
max_profit = 0

for i in range(size):
  for j in range(i+1, size):
    if array[j] - array[i] > max_profit:
      max_profit = array[j] - array[i]

print(max_profit)
```
### Solution | C++
```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
  vector<int> arr;
  int size, max_profit = 0, x;
  
  cin>>size;
  for (int i=0; i<size; i++) {
    cin>>x;
    arr.push_back(x);
  }

  for (int i=0; i<size; i++) {
    for (int j=i+1; j<size; j++) {
      if (arr[j] - arr[i] > max_profit) 
        max_profit = arr[j] - arr[i];
    }
  }

  cout<<max_profit;
  return 0;
}
```
### Approach 2:
>**Keep track on Minimum Price and Maximum Profit.**

**:stopwatch: Time Complexity - O(n).**    
**:floppy_disk: Space Complexity - O(1).** 

### Solution | Python
```python
array = [int(x) for x in input().split()]
max_profit = 0
min_price = float('inf')

for price in array:
      max_profit = max(max_profit, price - min_price)
      min_price = min(min_price, price)

print(max_profit)
```
### Solution | C++
```cpp
#include <iostream>
#include <vector>
#include <algorithm>
#include <limits>
using namespace std;

int main() {
  vector<int> arr;
  int size, max_profit = 0, min_price = numeric_limits<int>::max(), x;
  cin>>size;
  for (int i=0; i<size; i++) {
    cin>>x;
    arr.push_back(x);
  }

  for (int price: arr) {
    max_profit = max(max_profit, price - min_price);
    min_price = min(min_price, price);
  }

  cout<<max_profit;
  return 0;
}
```
```
Note: 
1. <algorithm> header is used for min() and max().
2. <limits> header is used for numeric_limits<int>::max().
```

### Reference
**:arrow_forward: [Youtube](https://www.youtube.com/watch?v=hOLSBR7eN4g)**  

### Practice
**:memo: [LeetCode](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)**

|**:house: [HOME](https://github.com/theInvincible/Daily-Coding-Problem/)**|
|--------------------------------------------------------------------------|
