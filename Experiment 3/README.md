# Experiment 03: Construct a Binary Tree from User Inputs and Perform Pre-order, In-order, and Post-order Traversals

## Aim
To construct a Binary Search Tree (BST) from user inputs and perform Pre-order, In-order, and Post-order traversals to visit nodes in different recursive orders.

## Requirements
- Java JDK 8 or later
- Command Prompt, PowerShell, VS Code, IntelliJ IDEA, or any Java-compatible IDE

## How to Compile
```bash
javac BST_Traversals.java
```

## How to Run
```bash
java BST_Traversals.java
```

## Algorithm
1. Initialize an empty Binary Search Tree with `root = null`.
2. For each key provided by the user, insert it into the BST recursively:
   - If the root is null, allocate and return a new node with the value.
   - If the value is strictly less than the current node's value, recursively insert it into the left subtree.
   - If the value is strictly greater than the current node's value, recursively insert it into the right subtree.
3. Compute the tree height and render the tree diagram using a 2D canvas.
4. Perform recursive tree traversals:
   - **Pre-order Traversal:** Visit Current Node $\rightarrow$ Traverse Left Subtree $\rightarrow$ Traverse Right Subtree.
   - **In-order Traversal:** Traverse Left Subtree $\rightarrow$ Visit Current Node $\rightarrow$ Traverse Right Subtree (produces values in ascending sorted order).
   - **Post-order Traversal:** Traverse Left Subtree $\rightarrow$ Traverse Right Subtree $\rightarrow$ Visit Current Node.

## Example

**Input:**
```plaintext
Enter values to insert into BST (space-separated on a single line):
Example: 50 30 70 20 40 60 80
Input: 50 30 70 20 40 60 80
```

**Output:**
```plaintext
--- Binary Search Tree Diagram ---
              50
       /______________\
      30              70
   /__  __\        /__  __\
  20      40      60      80

Pre-order Traversal  : 50 30 20 40 70 60 80 
In-order Traversal   : 20 30 40 50 60 70 80 
Post-order Traversal : 20 40 30 60 80 70 50 
```

## Complexity
- **Time Complexity:**
  - **Tree Construction:**
    - Best Case: $O(n \log n)$ (balanced tree insertions)
    - Average Case: $O(n \log n)$
    - Worst Case: $O(n^2)$ (degenerate/skewed tree)
  - **Traversals (Pre-order, In-order, Post-order):**
    - $O(n)$ where every node is visited exactly once
- **Space Complexity:**
  - $O(h)$ auxiliary recursion stack space, where $h$ is the tree height ($O(\log n)$ for balanced trees, $O(n)$ in the worst case for skewed trees)
  - $O(n)$ space for storing tree nodes

## Conclusion
The experiment successfully constructs a Binary Search Tree from dynamic user input and demonstrates recursive Pre-order, In-order, and Post-order traversals in Java. The observed output validates that In-order traversal of a BST consistently retrieves keys in ascending order.
