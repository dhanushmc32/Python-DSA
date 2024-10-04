class Node:
    """
    Node class represents an element in a linked list.
    It contains data and a reference to the next node.
    """
    def __init__(self, value):
        self.data = value  # Value stored in the node
        self.next = None   # Pointer to the next node


class LinkedList:
    """
    LinkedList class provides basic linked list functionality such as insertion, 
    deletion, searching, and traversal.
    """
    def __init__(self):
        self.head = None  # Points to the first node in the list
        self.n = 0        # Tracks the number of nodes in the list

    def __len__(self):
        """
        Returns the current size of the linked list.
        """
        return self.n

    def insert_head(self, value):
        """
        Inserts a new node at the head (beginning) of the list.
        """
        new_node = Node(value)   # Create a new node
        new_node.next = self.head  # Set the next of new node to current head
        self.head = new_node  # Update head to the new node
        self.n = self.n + 1   # Increment the node count

    def __str__(self):
        """
        Returns a string representation of the linked list in the format 'data->data->...'
        If the list is empty, returns 'Empty List'.
        """
        curr = self.head
        result = ""
        while curr is not None:  # Traverse the list and append each node's data
            result += str(curr.data) + "->"
            curr = curr.next
        return result[:-2] if result else "Empty List"  # Remove the trailing '->'

    def append(self, value):
        """
        Appends a new node to the end of the list.
        """
        new_node = Node(value)  # Create a new node
        if self.head is None:  # If the list is empty, set the new node as head
            self.head = new_node
            self.n = self.n + 1
            return
        curr = self.head
        while curr.next is not None:  # Traverse to the last node
            curr = curr.next
        curr.next = new_node  # Append the new node
        self.n = self.n + 1

    def insert_after(self, after, value):
        """
        Inserts a new node with the given value after a node with the 'after' value.
        """
        new_node = Node(value)
        curr = self.head
        while curr is not None:  # Traverse the list to find the 'after' node
            if curr.data == after:
                break
            curr = curr.next
        if curr is not None:  # Insert the new node after the found node
            new_node.next = curr.next
            curr.next = new_node
            self.n = self.n + 1
        else:
            return "item not found"  # If 'after' node is not found

    def clear(self):
        """
        Clears the entire linked list.
        """
        self.head = None  # Set head to None to remove all references to nodes
        self.n = 0  # Reset node count to 0

    def delete_head(self):
        """
        Removes the first node (head) from the list.
        """
        if self.head is None:  # If the list is empty
            return "empty linked list"
        self.head = self.head.next  # Move head to the next node
        self.n = self.n - 1  # Decrement the node count

    def pop(self):
        """
        Removes the last node from the list.
        """
        if self.head is None:  # If the list is empty
            return "Empty LL"
        curr = self.head
        if curr.next is None:  # If the list has only one node
            return self.delete_head()  # Call delete_head to remove the single node
        while curr.next.next is not None:  # Traverse to the second-to-last node
            curr = curr.next
        curr.next = None  # Remove the last node
        self.n = self.n - 1

    def remove(self, value):
        """
        Removes the first node with the given value from the list.
        """
        if self.head is None:  # If the list is empty
            return "Empty ll"
        if self.head.data == value:  # If the head node holds the value
            return self.delete_head()  # Call delete_head to remove it
        curr = self.head
        while curr.next is not None:  # Traverse to find the node before the one to be removed
            if curr.next.data == value:
                break
            curr = curr.next
        if curr.next is None:  # If the value is not found in the list
            return "not found"
        else:
            curr.next = curr.next.next  # Remove the node by updating the next pointer

    def search(self, item):
        """
        Searches for the first occurrence of the given item and returns its position.
        Returns 'not found' if the item is not in the list.
        """
        curr = self.head
        pos = 0
        while curr is not None:  # Traverse the list
            if curr.data == item:
                return pos  # Return position if found
            curr = curr.next
            pos = pos + 1
        return "not found"

    def __getitem__(self, index):
        """
        Returns the data of the node at the given index.
        """
        curr = self.head
        pos = 0
        while curr is not None:  # Traverse to the index
            if pos == index:
                return curr.data  # Return the data at the index
            curr = curr.next
            pos = pos + 1
        return "index error"  # Return an error if the index is out of range


# Example usage
L = LinkedList()
L.insert_head(1)
L.insert_head(2)
L.insert_head(3)
L.pop()  # Removes the last node
L.pop()
L.pop()
L.pop()  # Attempts to remove from an empty list
print(L)  # Should print "Empty List"
