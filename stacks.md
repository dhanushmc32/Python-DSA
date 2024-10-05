
# Stack Implementation using Linked List

This project implements a **Stack** data structure using a **Linked List** in Python. It consists of two classes: `Node` and `Stack`. The `Node` class represents an individual element in the stack, while the `Stack` class manages the stack operations like **push**, **pop**, **peak**, and **traverse**.

## Table of Contents
- [Overview](#overview)
- [Classes](#classes)
  - [Node Class](#node-class)
  - [Stack Class](#stack-class)
- [Methods](#methods)
  - [isempty()](#isempty)
  - [push()](#push)
  - [traverse()](#traverse)
  - [peak()](#peak)
  - [pop()](#pop)
- [Code](#code)
- [How to Use](#how-to-use)

## Overview

A **stack** is a Last In, First Out (LIFO) data structure, meaning the last element added to the stack is the first one to be removed. This project demonstrates the stack's functionality using linked nodes rather than arrays or lists, allowing for dynamic size growth.

## Classes

### Node Class

The `Node` class represents each element in the stack. It has two attributes:

- **data**: Stores the value of the node.
- **next**: Points to the next node in the stack.

### Stack Class

The `Stack` class implements the stack operations. It uses a linked list to keep track of the elements, with the top of the stack represented by the `top` pointer.

## Methods

### isempty()
- **Description**: Checks whether the stack is empty.
- **Returns**: `True` if the stack is empty, `False` otherwise.

### push(value)
- **Description**: Adds a new element to the top of the stack.
- **Parameters**: `value` - The data to be added to the stack.
- **Behavior**: Creates a new node with the given value and pushes it onto the stack by linking it to the current top node.

### traverse()
- **Description**: Prints all elements in the stack starting from the top.
- **Behavior**: Traverses through each node in the stack and prints its data.

### peak()
- **Description**: Returns the top element of the stack without removing it.
- **Returns**: The data of the top element, or "stack empty" if the stack is empty.

### pop()
- **Description**: Removes and returns the top element of the stack.
- **Returns**: The data of the removed element, or "stack empty" if the stack is empty.

## Code

Here is the complete implementation of the stack using a linked list:

```python
class Node:
    # Node class represents an element in the stack
    def __init__(self, value):
        self.data = value  # Data to be stored in the node
        self.next = None   # Pointer to the next node

class Stack:
    # Stack class to represent a stack data structure using linked nodes
    def __init__(self):
        self.top = None  # Top points to the top element of the stack

    def isempty(self):
        # Check if the stack is empty
        return self.top == None

    def push(self, value):
        # Create a new node and push it onto the stack
        new_node = Node(value)
        new_node.next = self.top  # Link the new node to the current top
        self.top = new_node       # Update the top to the new node

    def traverse(self):
        # Traverse and print all elements in the stack
        temp = self.top
        while temp != None:  # Loop until the end of the stack (None)
            print(temp.data) # Print the current node's data
            temp = temp.next # Move to the next node

    def peak(self):
        # Return the top element without removing it (peek operation)
        if self.isempty():  # If the stack is empty, return an appropriate message
            return "stack empty"
        else:
            return self.top.data  # Return the top element's data

    def pop(self):
        # Pop the top element from the stack and return its value
        if self.isempty():  # If the stack is empty, return an appropriate message
            return "stack empty"
        else:
            data = self.top.data  # Store the top element's data
            self.top = self.top.next  # Move the top to the next element
            return data  # Return the popped element's data
```

## How to Use

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/stack-implementation.git
   ```

2. **Navigate to the project directory**:
   ```bash
   cd stack-implementation
   ```

3. **Run the script**:
   You can use this implementation by creating an instance of the `Stack` class and using its methods:

   ```python
   stack = Stack()
   stack.push(10)
   stack.push(20)
   stack.push(30)

   print("Stack elements:")
   stack.traverse()

   print("Top element:", stack.peak())

   print("Popped element:", stack.pop())
   ```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

This README file now includes the complete code for the `Stack` implementation, making it easy to understand and use for anyone who checks out your repository.
