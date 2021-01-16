Asked by Palantir.

Write a program that checks whether an integer is a palindrome. 
For example, `121` is a palindrome, as well as `888`. `678` is not a palindrome. 
Do not convert the integer into a string.

<details>
  <summary>Python</summary>
  
  ```python
  def is_palindrome(n):
    t = n
    r = 0
    
    if (n < 0):
        return False
        
    while (t):
        r = (r * 10) + (t % 10)
        t = int(t/10)

    if (n == r):
        return True

    return False
    
if __name__ == '__main__':
    
    print(is_palindrome(121))
    
    print(is_palindrome(888))
    
    print(is_palindrome(678))
  ```
</details>

<details>
  <summary>C++</summary>
  
  ```cpp
  #include <iostream>
  using namespace std;

  bool is_palindrome(int n) {
      int t = n, r = 0;

      if (n < 0)
          return false;

      while (t) {
          r = (r * 10) + (t % 10);
          t /= 10;
      }

      if (n == r)
          return true;

      return false;
  }

  int main() {
      cout << (is_palindrome(121) ? "True" : "False") << endl;

      cout << (is_palindrome(888) ? "True" : "False") << endl;

      cout << (is_palindrome(678) ? "True" : "False") << endl;
  }
  ```
</details>
