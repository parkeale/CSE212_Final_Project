# Binary Trees
- Binary Tree is a special type of data structure. It is similar to a linked list. The start of the data structure  is the root( the top node). A node that is connected to two other nodes is called the parent, and the nodes connected to the parent are called the child. Nodes with no connections are called leaves. 
![Tree example](tree_structure.jpg) 

- Binary search tree Binary Search Tree: 
In a Binary search tree data is placed into the nodes in a specific manner.  Values of data less than a parent node are put on the left. Values greater are put on the right. Organizing data like this allows for fast iteration of the data.  Meaning you can look up, remove and insert data in a efficient manner. The operation time becomes O(log n) instead of O(n).

## Binary Tree Commands

| Operation               | Description                                | Big O Performance |
| ------------------------| -------------------------------------------| ----------------- |
| insert(value)           | Insert Value into the tree                 | Olog(n)           |
| remove(value)           | Remove a value from the tree               | Olog(n)           |
|contains(value)          | Finds if value is in tree                  | Olog(n)           |
|forward_traverse         | Visits all values from smallest to largest | O(n)              |
|backwards_traverse       | Visits all values from largest to smallest | O(n)              |
|height(node)             | Determine Height of BST                    | O(n)              |
|size()                   | Return size of the BST                     | O(1)              |
|empty()                  | Checks for empty list                      | O(1)              |
## Example of Binary Search Tree
Practice studying others code by understanding this binary search tree. 
```python
class BST:

    class Node:

        def __init__(self, data):
            self.data = data
            self.left = None
            self.right = None

    def __init__(self):
        """
        Initialize an empty BST.
        """
        self.root = None

    def insert(self, data):
        if self.root is None:
            self.root = BST.Node(data)
        else:
            self._insert(data, self.root)  # Start at the root

    def _insert(self, data, node):

        if data < node.data:
            # The data belongs on the left side.
            if node.left is None:
                if data != node.data:
                    node.left = BST.Node(data)
            else:
                # recursively on the left sub-tree.
                self._insert(data, node.left)
        else:
            # The data belongs on the right side.
            if node.right is None:
                if data != node.data:
                    node.right = BST.Node(data)
            else:
                # recursively on the right sub-tree.
                self._insert(data, node.right)
    
    def __contains__(self, data):

        return self._contains(data, self.root)


    def _contains(self, data, node):
        """ The function will search for a node with data
        """
        if data == node.data:
            return True
        elif data < node.data:
            # The data belongs on the left side.
            if node.left is None:
                return False
                # Data was not found
            else:
                # Need to keep looking.  Call _insert
                # recursively on the left sub-tree.
                return self._contains(data, node.left)

        else:
            # The data belongs on the right side.
            if node.right is None:
                # Data was not found
                return False
            else:
                # Need to keep looking.  Call _conversion
                # recursively on the right sub-tree.
                return self._contains(data, node.right)
        # use recursion to pass through the tree

    def __iter__(self):
        yield from self._traverse_forward(self.root)  # Start at the root
        
    def _traverse_forward(self, node):
        """
        Does a forward traversal (in-order traversal).
        """
        if node is not None:
            yield from self._traverse_forward(node.left)
            yield node.data
            yield from self._traverse_forward(node.right)
        
    def __reversed__(self):
        """
        Perform a formward traverse (starting from the root) 
        """        
        yield from self._traverse_backward(self.root) 

    def _traverse_backward(self, node):
        """
        Does a backwards traverse.     
        """
        if node is not None:
            yield from self._traverse_backward(node.right)
            yield node.data
            yield from self._traverse_backward(node.left)
````



## Challange Problem 
- Create a binary search tree with famous cities. Have letters like A B C be the small values, and letter like X, Y, Z be the large values. format the tree to insert remove, and search for the cities. Model the code after the example given above. 
