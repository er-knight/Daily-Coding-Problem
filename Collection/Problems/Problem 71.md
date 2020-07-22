## Problem 71
***Asked by Two Sigma.***
## Task
**Using a function rand7() that returns an integer from 1 to 7 (inclusive) with uniform probability, implement a function rand5() that returns an integer from 1 to 5 (inclusive).**

### Approach
```
7 * rand7() + rand7() - 7
```
>**Above formula returns an integer from 1 to 49 (inclusive).**  
>**If** `integer < 45` **, return** `(integer % 5) + 1` **.**  
 
### Solution | Python
```python
def rand7():
  # returns an integer from 1 to 7 (inclusive) with uniform probability

def rand5():
  num = (7 * rand7() + rand7() - 7)
  if num < 45:
    return ((num % 5) + 1)
  else:
    return 0
```
### Solution | C++
```cpp
int rand7() {
  /* returns an integer from 1 to 7 (inclusive) with uniform probability */
}

int rand5() {
  int num = 0;
  num = (7 * rand7() + rand7() - 7);
  if (num < 45)
    return ((num % 5) + 1);
  else
    return 0;
}    
```


|**:file_folder: [INDEX](https://github.com/theInvincible/Daily-Coding-Problem/blob/master/Collection/INDEX.md)**|
|------------------------------------------------------------------------------------------------------------------------|
