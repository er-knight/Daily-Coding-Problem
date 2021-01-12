Asked by Facebook.

Given an array of integers in which two elements appear exactly once and all other elements appear exactly twice, find the two elements that appear only once.

For example, given the array `[2, 4, 6, 8, 10, 2, 6, 10]`, return `4` and `8`. The order does not matter.

Follow-up: Can you do this in linear time and constant space?

<details>
  <summary>Solution</summary>
  
```python
array = [2, 4, 6, 8, 10, 2, 6, 10]
map_ = {}

for i in array:
    map_[i] = map_.get(i, 0) + 1

for n in  map_.keys():
    if (map_[n] == 1):
        print(n)
```
</details>
