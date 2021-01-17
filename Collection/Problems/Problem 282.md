Asked by Netflix.

<img src="https://img.shields.io/badge/-two--pointer-wheat">
Given an array of integers, determine whether it contains a Pythagorean triplet. Recall that a Pythogorean triplet `(a, b, c)` is defined by the equation <samp>a<sup>2</sup> + b<sup>2</sup> = c<sup>2</sup></samp>.

<details>
<summary>Python</summary>

```python
def find_triplet(a):
  a.sort()
  for i in range(len(a)):
      j = 0
      k = len(a) - 1
      while (j < k):
          if ((a[j] * a[j] + a[k] * a[k]) < (a[i] * a[i])):
              j += 1
          elif ((a[j] * a[j] + a[k] * a[k]) > (a[i] * a[i])):
              k -= 1
          else:
              return True

  return False

if __name__ == "__main__":

  a = [1, 2, 3, 4, 5]

  print(find_triplet(a))

  a = [1, 3, 6, 2, 8]

  print(find_triplet(a))
```
</details>
