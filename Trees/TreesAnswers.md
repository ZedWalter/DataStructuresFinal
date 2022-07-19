```python

def delete(self, data):
    # Call the function starting with the root.
    self._delete(data, self.root)

def _delete(self, data, node):
    # Establish our base case
    if node is None:
        print("Data not found.")
    elif data < node.data:
        self._delete(data, node.left)
    elif data > node.data:
        self._delete(data, node.right)
    else:
        # We found the node with our data.
        # Now we check for child nodes.
        # If node is empty, no problem, delete the node
        if node.left is None and node.right is None:
            node = None
        #If the node has only a right child, replace it with that node
        elif node.left is None:
            node = node.right
        #If the node has only a left child, replace it with that node
        elif node.right is None:
            node = node.left
        else:
            # If there are two child nodes, find the smaller of the two numbers in the right tree
            # This is the inorder successor
            temp = node.right
            while temp.left is not None:
                temp = temp.left
            node.data = temp.data
            self._delete(temp.data, node.right)
        print(f'{data} Deleted')
```
