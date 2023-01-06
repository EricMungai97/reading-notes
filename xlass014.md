# Trees

[SOURCE](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/Trees.html)

**Common Terminology**

`Node` - A Tree node is a component which may contain its own values, and references to other nodes

`Root` - The root is the node at the beginning of the tree

`K` - A number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2.

`Left` - A reference to one child node, in a binary tree

`Right` - A reference to the other child node, in a binary tree

`Edge` - The edge in a tree is the link between a parent and child node

`Leaf` - A leaf is a node that does not have any children

`Height` - The height of a tree is the number of edges from the root to the furthest leaf

![Sample Tree](/images/BinaryTree1.png)

**Traversals**

Traversing a tree allows us to search for a node, print out the contents of a tree, and much more! There are two categories of traversals when it comes to trees:

* Depth First 

* Breadth First

**Depth First**

Depth first traversal is where we prioritize going through the depth `(height)` of the tree first. There are multiple ways to carry out depth first traversal, and each method changes the order in which we search/print the root. Here are three methods for depth first traversal:

`Pre-order`: root >> left >> right

Pre-order means that the root has to be looked at first. Looking at the root means we just output its value.

***Pseudo Code***

```
ALGORITHM preOrder(root)
// INPUT <-- root node
// OUTPUT <-- pre-order output of tree node's values

    OUTPUT <-- root.value

    if root.left is not Null
        preOrder(root.left)

    if root.right is not NULL
        preOrder(root.right)
```


`In-order`: left >> root >> right

***Psuedo Code***

```
ALGORITHM inOrder(root)
// INPUT <-- root node
// OUTPUT <-- in-order output of tree node's values

    if root.left is not NULL
        inOrder(root.left)

    OUTPUT <-- root.value

    if root.right is not NULL
        inOrder(root.right)
```

`Post-order`: left >> right >> root

```
ALGORITHM postOrder(root)
// INPUT <-- root node
// OUTPUT <-- post-order output of tree node's values

    if root.left is not NULL
        postOrder(root.left)

    if root.right is not NULL
        postOrder(root.right)

```

![depth first](/images/tree-example.png)

Given the sample tree above, our traversals would result in different paths:

Pre-order: A, B, D, E, C, F

In-order: D, B, E, A, F, C

Post-order: D, E, B, F, C, A

The most common way to traverse through a tree is to use `recursion`. With these traversals, we rely on the call stack to navigate back up the tree when we have reached the end of a sub-path.

**Breadth First**

Breadth first traversal iterates through the tree by going through each level of the tree node-by-node. So, given our starting tree one more time:

Our output using breadth first traversal is now:

Output:`A, B, C, D, E, F`

Traditionally, breadth first traversal uses a `queue `(instead of the call stack via recursion) to traverse the width/breadth of the tree.

**Pseudocode**

```
ALGORITHM breadthFirst(root)
// INPUT  <-- root node
// OUTPUT <-- front node of queue to console

  Queue breadth <-- new Queue()
  breadth.enqueue(root)

  while ! breadth.is_empty()
    node front = breadth.dequeue()
    OUTPUT <-- front.value

    if front.left is not NULL
      breadth.enqueue(front.left)

    if front.right is not NULL
      breadth.enqueue(front.right)
```

`Binary Trees` restrict the number of children to two (hence our left and right children).

There is no specific sorting order for a binary tree. Nodes can be added into a binary tree wherever space allows.

## K-ary Trees

If Nodes are able have more than 2 child nodes, we call the tree that contains them a `K-ary Tree`. In this type of tree we use `K` to refer to the maximum number of children that each Node is able to have.

**Breadth First Traversal**

Traversing a K-ary tree requires a similar approach to the breadth first traversal. We are still pushing nodes into a queue, but we are now moving down a list of children of length k, instead of checking for the presence of a left and a right child.

![K-ary Tree](/images/KaryTree1.png)

If we traversed this tree Breadth First we should see the output:

Output: `A, B, C, D, E, F, G, H`

**Pseudocode**

```
ALGORITHM breadthFirst(root)
// INPUT  <-- root node
// OUTPUT <-- front node of queue to console

  Queue breadth <-- new Queue()
  breadth.enqueue(root)

  while ! breadth.is_empty()
    node front = breadth.dequeue()
    OUTPUT <-- front.value

    for child in front.children
        breadth.enqueue(child)
```

### Binary Search Trees

A Binary Search Tree (BST) is a type of tree that does have some structure attached to it. In a BST, nodes are organized in a manner where all values that are smaller than the root are placed to the left, and all values that are larger than the root are placed to the right.

![Binary Search Tree](/images/BST1.png)

**Searching a BST**

Searching a BST can be done quickly, because all you do is compare the node you are searching for against the root of the tree or sub-tree. If the value is smaller, you only traverse the left side. If the value is larger, you only traverse the right side.

***Big O***

The Big O time complexity of a Binary Search Tree’s insertion and search operations is `O(h)`, or `O(height)`. In the worst case, we will have to search all the way down to a leaf, which will require searching through as many nodes as the tree is tall. In a balanced (or “perfect”) tree, the height of the tree is log(n). In an unbalanced tree, the worst case height of the tree is n.

The Big O space complexity of a BST search would be `O(1)`. During a search, we are not allocating any additional space.
