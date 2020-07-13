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
- ***Dequeue() - O(n), becuase we need to remove all element from primaryStack which takes O(n) time.***

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
        for i in range(len(self.primaryStack)-1, 0, -1):
            self.secondaryStack.append(self.primaryStack.pop(i))
        self.primaryStack.pop(0)
        for i in range(len(self.secondaryStack)-1, -1, -1):
            self.primaryStack.append(self.secondaryStack.pop(i))

    def Show(self):
        print('Queue:', end=' ')
        for i in self.primaryStack:
            print(i, end=' ')
        print()
```
```python
myQueue = Queue()
myQueue.Enqueue(5)
myQueue.Enqueue(4)
myQueue.Enqueue(3)
myQueue.Enqueue(2)
myQueue.Show() # 5 4 3 2
myQueue.Dequeue()
myQueue.Show() # 4 3 2
```
