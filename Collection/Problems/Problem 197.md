Asked by Amazon.

<kbd>array</kbd>

Given an array and a number `k` that's smaller than the length of the array, rotate the array to the right `k` elements in-place.

<details>
  <summary>Solution</summary>
  
```python
a = [2, 3, 1, 6, 4, 8]

k = 2 

k = len(a) - k # comment this line to rotate left

while (k > 0):
    for i in range(len(a)-1):
        a[i], a[i+1] = a[i+1], a[i]
    k -= 1
    
print(a)
```
</details>
