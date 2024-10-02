# Neetcode

[Neetcode.io](https://neetcode.io/practice) documents 75 common algorithms used in interviews. Here are my notes on them.

## Table of contents
<!-- TO BE ADDED -->

## Template
<!-- START OF COPY -->
### X. 

**Source :** []
**Description :**
**Data format :**

**Solution :**
- 
<!-- END OF COPY -->

## Array and hashing

## Two pointers

## Sliding window

## Stack

## Binary search

## Linked list

## Trees

### 1. Inversion of a binary tree

**Source :** [https://neetcode.io/problems/invert-a-binary-tree]
**Description :** Input tree. Return same tree, but flipped (right to left).
**Data format :** TreeNode : { value: any, left: ?TreeNode, right: ?TreeNode }

**Solution :** Use recursivity
- END condition : if node == null, return null
- create new TreeNode with current value
- new TreeNode.right = recursive call on current TreeNode.left
- same on the other side
- return new TreeNode (with flipped sides)

### 2. Depth of a binary tree

**Source :** [https://neetcode.io/problems/depth-of-binary-tree]
**Description :** Input tree. Return number of nodes between root and farthest leaf.
**Data format :** TreeNode : { value: any, left: ?TreeNode, right: ?TreeNode }

**Solution :** Use recursivity
- END condition : if node == null, return 0
- recursive call on node.right and node.left
- find biggest value between the two
- return 1 + biggest value

### 3. Diameter of a binary tree

**Source :** [https://neetcode.io/problems/binary-tree-diameter]
**Description :** Input tree. Return biggest number of edges between farthest leaves/nodes.
**Data format :** TreeNode : { value: any, left: ?TreeNode, right: ?TreeNode }

**Solution :** Depth-First Search + Recursivity
- Create an independent global diameter value
- Make a recursive function that takes a Node and returns the biggest depth below + verify current diameter
  - END condition : if node == null, return 0
  - recursive call on node.right and node.left, and save depth result for each side
  - global diameter = MAX( tmp result OR ( depth left + depth right ) )
  - return 1 + MAX( depth left OR depth right)

### 4. Balance of a binary tree

**Source :** [https://neetcode.io/problems/balanced-binary-tree]
**Description :** Input tree. Return if branches have a length difference greater than 1.
**Data format :** TreeNode : { value: any, left: ?TreeNode, right: ?TreeNode }

**Solution :** Depth-First Search + Recursivity
- Create an independent global is balanced value that is set to true
- Make a recursive function that takes a Node and returns the biggest depth below + verify is balanced
  - END condition : if node == null, return 0
  - recursive call on node.right and node.left, and save depth result for each side
  - is NOT balanced = difference between depth left and right is not acceptable (greater than 1)
    - => BREAK possible here
  - return 1 + MAX( depth left OR depth right)
 
### 5. Equality of a binary tree

**Source :** [https://neetcode.io/problems/same-binary-tree]
**Description :** Two input trees. Return if trees are exactly the same.
**Data format :** TreeNode : { value: any, left: ?TreeNode, right: ?TreeNode }

**Solution :** Use recursivity
- END condition : if nodeA == null AND nodeB == null, return true
- if nodeA.value == nodeB.value
  - recursive call on left nodes
  - recursive call on right nodes
  - return result of both comparisons (AND)
- else return false

### 6. Subtree of a binary tree

**Source :** []
**Description :** Two input trees. Return if tree B is a subtree of tree A.
**Data format :** TreeNode : { value: any, left: ?TreeNode, right: ?TreeNode }

**Solution :** Use recursivity + use [Equality of a binary tree](<!-- TODO add proper link -->)
- END condition : if nodeA == null, return false
- END condition : if nodeB == null, return true
- END condition : if nodeA and nodeB are the same tree (make separate function for this logic), return true
- recursive call on nodeA.left and nodeB
- recursive call on nodeA.right and nodeB
- return result of both recursive calls (OR)

### 7. Lowest common ancestor in a binary tree

**Source :** []
**Description :** Three input trees : data, A, and B. Return the closest common ancestor of A and B that exists in data.
**Assumption :** An ancestor can be a descendant of itself. A and B exist within data.
**Data format :** TreeNode : { value: any, left: ?TreeNode, right: ?TreeNode }

**Solution :** Use recursivity
- compare current.value with A.value and B.value
  - if current < ( A AND B ), recursive call with current.right
  - if current > ( A AND B ), recursive call with current.left
- END condition : return current

### 8. Level order traversal of a binary tree

**Source :** [https://neetcode.io/problems/level-order-traversal-of-binary-tree]
**Description :** Input tree. Ignore the branches and return tree data as horizontal levels.
**Data format :** TreeNode : { value: any, left: ?TreeNode, right: ?TreeNode }

**Solution :** Use recursivity
- Create an independent global result that is set to an emtpy array
- Make a recursive function that takes a list of Node and returns the node descendants
  - for each item in the list
    - add the value to a tmp level array
    - add the left and right nodes (if not null) to a descendant array
  - push the tmp level array into the global result variable
  - END condition : the list of descendants is empty
    - recursive call on the descendants
- First call on a list with only the current node, to start recursivity
- Return result 

## Heap / Priority queue

## Backtracking

## Tries

## Graphs

## Advanced graphs

## 1-D dynamic programming

## 2-D dynamic programming

## Greedy

## Intervals

## Math & geometry

## Bit manipulation
