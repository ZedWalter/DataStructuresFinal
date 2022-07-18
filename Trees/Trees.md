**Data Structure 3: Trees**


---

## **Introduction**

Trees are a lot like the linked lists that we just learned about. They are made up of nodes and each node is connected to each other by pointers. The thing that makes trees unique from linked lists, is that nodes can connect to multiple different noedes. Trees is actually a overall category and is often broken up into 3 subcategories: binary, binary search, and balanced binary search.

#### Understanding Trees
If we extrapolate from the binary in the name binary trees we can initiall understand that there is 2. But 2 of what? Trees allow you to connect a node to multiple other nodes, binary trees limit these node connections to just 2. depending on where these nodes are in a given tree, we give them different names. Refer to the image below to see what position gives each node it's category.

<!-- Stack image -->
<figure>
<img src="https://scaler.com/topics/images/tree-data-structure-terminologies.webp">
<figcaption align= "center"> <a href="https://www.scaler.com/topics/data-structures/tree-data-structure/">Image source</a></figcaption>
</figure>

The first node is always called a root node and there can only ever be one of them. After that we have parent nodes, these are nodes that have child nodes underneath them and if it's a child node with no children under it, it is called a leaf.

A binary search tree (BST) is a binary tree that has a ruleset for the data put within it. Data that gets put into a BST is compared to each root/parent node to determin where it's final location in the tree should be. In general, smaller numbers go on the left of the root/parent while larger numbersgo on the right. By using this method the data within the tree becomes sorted and that allows for much faster operations.

To further increase the speeds of our operations we come to the last subcategory of tree, a balanced BST. What a balanced BST does is exactly in the name, it prevents one side of the tree from becoming much larger then the other. If one side becomes to large, it shuffles the nodes around until each branch of the root node is relatively even in size. An easy way to do this is to check the height of each side of the tree. If one side exceeds the height of the other side by 2 then some balancing needs to occur. Many different programs have been created to detect and solve unbalanced binary trees.

<figure>
<img src="https://stanford.edu/class/archive/cs/cs106b/cs106b.1158/images/balanced-tree-figure.png">
<figcaption align = "center"> <a href="https://stanford.edu/class/archive/cs/cs106b/cs106b.1158/preview-balanced-tree.shtml">Image Source</a></figcaption>
</figure>

### Understanding Tree operations
Lets first talk about inserting into a tree.


```python
def insert(self, data):
  #Insert into the tree. If the tree is empty the first input will become the root.
	if self.root is None:
		self.root = BST.Node(data)
	else:
		self._insert(data, self.root)  # Start at the root

def _insert(self, data, node):
	if data < node.data:
		# We traverse left if the data is smaller.
		if node.left is None:
			# If the spot is empty, place our data there.
			node.left = BST.Node(data)
		else:
			# If there is no spot, call the function again passing in our current location.
			self._insert(data, node.left)
	elif data >= node.data:
		# We traverse right if the data is bigger.
		if node.right is None:
			# If the spot is empty, place our data there.
			node.right = BST.Node(data)
		else:
			# If there is no spot, call the function again passing in our current location.
			self._insert(data, node.right)
```

Inserting and traversing through the tree is done recursively. You would not want to manually figure out how many times you need to loop to find a spot for your data. Because we use a balanced BST, inserting, finding, or removing data from the tree only take O(log n) time. 


```python
  # Size/Empty
  def size_empty(stack)
    length = len(stack)   # This line determines the size of the stack.
    return if length == 0: # This line returns true if the size is empty.
```

### Big O Efficiency & Limitations



### Strengths & Real World Applications



### Coding example




## Problem set


[Solution](TreeAnswers.md)
