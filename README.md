# red_black_tree


A Red-Black Tree is a self-balancing binary search tree where each node stores an additional bit that signifies the color of the node, either red or black. The tree maintains its balance by enforcing a set of properties that ensure the tree remains approximately balanced, thus providing O(log n) time complexity for search, insertion, and deletion operations.


Every node is either red (R) or black (B).
The root of the tree is always black (B).
All leaves (NIL nodes, or null pointers) are black (B). These are sometimes represented as sentinel nodes.
If a node is red (R), then both of its children must be black (B). This prevents two consecutive red nodes on any path from the root to a leaf.
For each node, every path from the node to its descendant leaves contains the same number of black nodes. This number is called the "black height" of the node.


To maintain these properties during insertion and deletion, Red-Black Trees may perform the following rotations:

Left Rotation (L):
A left rotation around node x shifts the subtree rooted at x to the right:
  x                  y
   \                /
    y    ==>        x
   /                  \
  T2                   T2

Right Rotation (R):
A right rotation around node y shifts the subtree rooted at y to the left:
  y                  x
 /                  \
x    ==>              y
 \                    /
  T2                T2


Insertion in Red-Black Tree

Binary Search Tree Insertion:
Insert the node as in a regular binary search tree, coloring the new node red (R).

Fix Violations:
If the parent of the inserted node is red (R), then the Red Property is violated. The tree fixes this by:
Case 1: If the uncle (the sibling of the parent) is red, recolor the parent and uncle to black (B), and the grandparent to red (R), then recursively apply the fix to the grandparent.
Case 2: If the uncle is black (B), perform a rotation to fix the tree, and recolor appropriately to maintain the tree properties.

Root Check:
After fixing, the root is recolored to black (B) to maintain the Root Property


Deletion in Red-Black Tree

Binary Search Tree Deletion:
Remove the node as in a regular binary search tree.

Fix Violations:
If the deleted node was black (B), it could violate the Black Height Property. The tree fixes this by:
Case 1: If the sibling of the node is red (R), recolor the sibling and parent, and perform a rotation to move the red node up the tree.
Case 2: If the sibling is black (B) with black children, recolor the sibling red (R), and move the violation up the tree to the parent.
Case 3: If the sibling is black (B) with at least one red child, perform rotations and recoloring to restore the properties.

Root Check:
After fixing, the root remains black (B).
