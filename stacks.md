# Stack Data Structure Implementation in Python

This project provides a basic implementation of a **Stack** data structure using a singly linked list. The `Stack` class supports common stack operations, such as **push**, **pop**, **traverse**, **peek**, and checking if the stack is empty. Each element in the stack is represented by a `Node`, where the data and a reference to the next node in the stack are stored.

## Classes

### Node

The `Node` class represents an individual element in the stack.

#### Constructor

```python
def __init__(self, value):
    self.data = value
    self.next = None
