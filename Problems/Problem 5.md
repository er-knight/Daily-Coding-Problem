## Problem 5
***Asked by Jane Street.***
### Task
`cons(a, b)` **constructs a pair and** `car(pair)` **and** `cdr(pair)` **returns the first and last element of that pair.**  
**For example, car(cons(3, 4)) returns 3 and cdr(cons(3, 4)) returns 4.**

**Given this implementation of cons:**
```python
def cons(a, b):
    def pair(f):
        return f(a, b)
    return pair
```
**Implement** `car()` **and** `cdr()`**.**
### Code (Python)
```python
def cons(a, b):
  def pair(f):
    return f(a, b)
  return pair

def car(pair):
  return pair(lambda a,b: a)

def cdr(pair):
  return pair(lambda a,b: b)
```
### Driver Code
```python
print(car(cons(3, 4)))
print(cdr(cons(3, 4)))

```
### Output
**3**  
**4**

***[Back to Previous Page](https://github.com/theInvincible/Daily-Coding-Problem/)***
