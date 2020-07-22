## Problem 45
***Asked by [Two Sigma](https://www.twosigma.com/).***
## Task
**Using a function** `rand5()` **that returns an integer from 1 to 5 (inclusive) with uniform probability, implement a function** `rand7()` **that returns an integer from 1 to 7 (inclusive).**

### Approach
```
5 * rand5() + rand5() - 5
```
>**Above formula returns an integer from 1 to 25 (inclusive).**  
>**If** `integer < 22` **, return** `(integer % 7) + 1` **.**  
 
### Solution | Python
```python
def rand5():
  # returns an integer from 1 to 5 (inclusive) with uniform probability

def rand7():
  num = (5 * rand5() + rand5() - 5)
  if num < 22:
    return ((num % 7) + 1)
  else:
    return 0
```
### Solution | C++
```cpp
int rand5() {
  /* returns an integer from 1 to 5 (inclusive) with uniform probability */
}

int rand7() {
  int num = 0;
  num = (5 * rand5() + rand5() - 5);
  if (num < 22)
    return ((num % 7) + 1);
  else
    return 0;
}    
```

### Reference
**:green_book: [GeeksforGeeks](https://www.geeksforgeeks.org/generate-integer-from-1-to-7-with-equal-probability/)**

|**:house: [HOME](https://github.com/theInvincible/Daily-Coding-Problem/)**|
|--------------------------------------------------------------------------|
