# Python-DSA# LinkedList in Python

## Overview

This project implements a **singly linked list** in Python, providing basic operations such as:
- Insertion at the head and the tail.
- Deletion of the head and the last node.
- Searching for a value.
- Removing a specific node.
- Clearing the list.
- Accessing an element by index.

## Linked List Operations

- `insert_head(value)` - Inserts a new node with the given value at the head of the list.
- `append(value)` - Appends a new node with the given value at the end of the list.
- `insert_after(after, value)` - Inserts a new node with the given value after a specified node.
- `clear()` - Clears the entire list.
- `delete_head()` - Deletes the head (first node) of the list.
- `pop()` - Deletes the last node of the list.
- `remove(value)` - Removes the first node with the specified value.
- `search(item)` - Searches for a node with the given value and returns its position.
- `__getitem__(index)` - Returns the value of the node at the specified index.
- `__len__()` - Returns the number of elements in the list.
- `__str__()` - Returns a string representation of the linked list.

## Example Usage

```python
L = LinkedList()

# Insert elements at the head
L.insert_head(1)
L.insert_head(2)
L.insert_head(3)

# Pop elements (remove from the end)
L.pop()

# Print the list
print(L)  # Output: 2->1
