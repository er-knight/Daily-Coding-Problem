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
