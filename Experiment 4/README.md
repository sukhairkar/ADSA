# Experiment 04: Construct a Binary Tree, Perform Traversals, and Search for a Given Key

## Aim
To construct a Binary Search Tree (BST), perform traversals of the constructed tree, and search for a given target key.

## Requirements
- Java JDK 8 or later
- Command Prompt, PowerShell, VS Code, IntelliJ IDEA, or any Java-compatible IDE

## How to Compile
```bash
javac BST_Search.java
```

## How to Run
```bash
java BST_Search.java
```

## Algorithm
1. Construct the Binary Search Tree from the user-specified space-separated numbers:
   - For each element, insert it recursively: values strictly less than the node value go into the left subtree, and values strictly greater go into the right subtree.
2. Render the ASCII diagram of the BST and display Pre-order, In-order, and Post-order traversal sequences.
3. Prompt the user for a search key $K$.
4. Implement recursive BST Search:
   - If current node is `null`, return `false` (key not present).
   - If current node data equals $K$, return `true` (key found).
   - If $K < \text{node.data}$, recursively search the left child: $\text{search}(\text{node.left}, K)$.
   - If $K > \text{node.data}$, recursively search the right child: $\text{search}(\text{node.right}, K)$.
5. Output whether the key is found or not found in the BST.

## Example

**Input:**
```plaintext
Enter values to insert into BST (space-separated on a single line):
Example: 50 30 70 20 40 60 80
Input: 50 30 70 20 40 60 80

Enter key to search: 40
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

Result: Key 40 is FOUND in the BST.
```

## Complexity
- **Time Complexity:**
  - **Search Operation:**
    - Best Case: $O(1)$ (target key resides at the root)
    - Average Case: $O(\log n)$ (balanced tree depth traversal)
    - Worst Case: $O(n)$ (degenerate/skewed linear tree)
  - **Tree Traversals:** $O(n)$
- **Space Complexity:**
  - $O(h)$ auxiliary recursion stack space where $h$ is tree height ($O(\log n)$ balanced, $O(n)$ worst case)
  - $O(n)$ space for tree nodes

## Conclusion
The experiment successfully implements BST creation, traversal, and key search in Java. It highlights the divide-and-conquer search property of Binary Search Trees, demonstrating $O(\log n)$ average-case search efficiency over linear searches.
