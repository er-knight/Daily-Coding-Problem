Asked by Stripe.

`reduce()` is a function that takes in an array, a combining function, and an initial value and builds up a result by calling the combining function on each element of the array, left to right.  
For example, we can write `sum()` in terms of `reduce()`:
```python
def add(a, b):
    return a + b

def sum(lst):
    return reduce(lst, add, 0)
```
This should call add on the initial value with the first element of the array, and then the result of that with the second element of the array, and so on until we reach the end, when we return the sum of the array.

Implement your own version of `reduce()`.

<details>
  <summary>Python</summary>
  
  ```python
  def reduce(a, f, s): 
      '''
      a => array
      f => function
      s => start
      '''
      for i in a:
          s = f(s, i)

      return s
    
  def add(a, b):
      return a + b

  def mul(a, b):
      return a * b

  a = [1, 2, 3, 4, 5]

  print(reduce(a, add, 0))

  print(reduce(a, mul, 1))
  ```
</details>
