## Problem 53
***Asked by Apple.***
### Task
**Implement a queue using two stacks. Recall that a queue is a FIFO (first-in, first-out) data structure with the following methods:**  
- `Enqueue()`**, which inserts an element into the queue.**
- `Dequeue()`**, which removes an element from the queue.**
### Approach
>**For** `Enqueue()` **, PUSH (i.e. append) element to primaryStack.**  
>**For** `Dequeue()` **, POP every element from primaryStack and PUSH(i.e. append) them (except element at bottom) to secondaryStack.**  
>**Before performing another** `Enqueue()` **, POP every element from secondaryStack and PUSH them to primaryStack.**

***Time Complexity -***
- ***Enqueue() - O(1).***
- ***Dequeue() - O(n), becuase we need to remove all element from primaryStack one by one, which takes O(n) time.***

***Space Complexity - O(n).***

### Solution | Python
```python
class Queue:
    def __init__(self):
        self.primaryStack = []
        self.secondaryStack = []

    def Enqueue(self, n):
        self.primaryStack.append(n)

    def Dequeue(self):
        if not(self.primaryStack):
            print('Queue is Empty!')
            return
        while len(self.primaryStack) != 1:
            self.secondaryStack.append(self.primaryStack.pop())

        x = self.primaryStack.pop(0)

        while (self.secondaryStack):
            self.primaryStack.append(self.secondaryStack.pop())
        
        print(x)
```
```python
myQueue = Queue()
myQueue.Enqueue(5)
myQueue.Enqueue(4)
myQueue.Enqueue(3)
myQueue.Enqueue(2)
myQueue.Dequeue() # 5
```
### Reference
**:green_book: [GeeksforGeeks](https://www.geeksforgeeks.org/queue-using-stacks/)**

|**:house: [HOME](https://github.com/theInvincible/Daily-Coding-Problem/)**|
|--------------------------------------------------------------------------|
