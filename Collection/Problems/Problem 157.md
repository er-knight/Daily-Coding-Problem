Asked by Amazon.

Given a string, determine whether any permutation of it is a palindrome.

For example, `carrace` should return true, since it can be rearranged to form `racecar`, which is a palindrome. `daily` should return false, since there's no rearrangement that can form a palindrome.

<details>
  <summary>Solution</summary>
  If frequency of atmost 1 letter is odd (and that of other letters is even), then one of its permutation is palindrome.
</details>
