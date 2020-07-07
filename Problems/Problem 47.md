## Problem 47
***Asked by Facebook.***
### Task
**Given a array of numbers representing the stock prices of a company in chronological order, write a function that calculates the maximum profit you could have made from buying and selling that stock once. You must buy before you can sell it.**
### Sample Input
**9 11 8 5 7 10**
### Sample Output
**5**
### Explanation
**Buy the stock at 5 dollars and sell it at 10 dollars.**

**Reference**
>**[Youtube](https://www.youtube.com/watch?v=hOLSBR7eN4g)**  
>**[LeetCode](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)**

**Simple Logic**
***Not Tested.***
```
for (current_price in prices) {
  if(current_min_price is less than current_price) {
    current_min_price = current_price
    current_max_price = current_price
  }
  else if (current_max_price is greater than current_price) {
    current_max_price = current_price
  }
}
```
