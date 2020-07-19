## Problem 27
***Asked by Facebook.***
### Task
**Given a string of round, curly, and square open and closing brackets, return whether the brackets are balanced (well-formed).**
>**First and only line of input contains a string consists of brackets.**

### Sample Input
**([])[]\({})**
### Sample Output
**True**
### Sample Input
**([)]**
### Sample Output
**False**
### Sample Input
**((()**
### Sample Output
**False**

### Approach
>**Iterate through the string.**
>>**If a Bracket is opening, add it to Stack.**  
>>**Else if a Bracket is closing, check for the matching opening bracket at the top of the Stack.**
>>>**If they are not matching, return False.**

>**After iterating through whole string, If the Stack is not empty return False, else return True.**

### Solution | Python
```python
def isBracketsBalanced(Expression):
    Stack = []
    for i in Expression:
        if i in ['(', '[', '{']:
            Stack.append(i)
        else:
            ch = Stack.pop()
            if (ch == '(' and i in ']}' ):
                return False
            elif (ch == '[' and i in ')}' ):
                return False
            elif (ch == '{' and i in ')]' ):
                return False
    if Stack:
        return False
        
    return True

Expression = input()
print(isBracketsBalanced(Expression))
```
### Solution | C++
```cpp
#include <iostream>
#include <string>
#include <vector>
using namespace std;

bool isBracketsBalanced(string Expression) {
  vector<char> Stack;
  for (auto i: Expression) {
    if (i == '(' || i == '[' || i == '{')
      Stack.push_back(i);
    else {
      char ch = Stack[Stack.size()-1];
      Stack.pop_back(); 
      if (ch == '(' && (i == ']' || i == '}'))
        return false;
      else if (ch == '[' && (i == ')' || i == '}'))
        return false;
      else if (ch == '{' && (i == ')' || i == ']'))
        return false;
    }
  }
  if (Stack.size() != 0)
    return false;

  return true;
}

int main() {
  string Expression;
  cin>>Expression;
  cout<<(isBracketsBalanced(Expression) ? "True" : "False");
}
```
**Reference: [GeeksforGeeks](https://www.geeksforgeeks.org/check-for-balanced-parentheses-in-an-expression/)**

:house: **[HOME](https://github.com/theInvincible/Daily-Coding-Problem/)**
