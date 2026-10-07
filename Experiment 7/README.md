# Experiment 07: Implement Prim's Algorithm

## Aim
To implement Prim's algorithm using a greedy approach to find the Minimum Spanning Tree (MST) of a weighted, connected, undirected graph represented as an adjacency matrix.

## Requirements
- Java JDK 8 or later
- Command Prompt, PowerShell, VS Code, IntelliJ IDEA, or any Java-compatible IDE

## How to Compile
```bash
javac Prims_Algorithm.java
```

## How to Run
```bash
java Prims_Algorithm.java
```

## Algorithm
1. Initialize arrays `key[]` of size $V$ with $\infty$ (`Integer.MAX_VALUE`), `parent[]` of size $V$, and boolean array `inMST[]` of size $V$ with `false`.
2. Set `key[0] = 0` and `parent[0] = -1` to designate vertex 0 as the starting node of the MST.
3. For $count = 0$ to $V - 2$:
   - Pick a vertex $u$ not yet included in MST (`!inMST[u]`) with the minimum `key` value.
   - Include $u$ in MST (`inMST[u] = true`).
   - For all adjacent vertices $v$ of $u$:
     - If $\text{graph}[u][v] \neq 0$, $v$ is not yet in MST, and $\text{graph}[u][v] < \text{key}[v]$:
       - Update `parent[v] = u`.
       - Update `key[v] = graph[u][v]`.
4. Print each edge $(parent[i], i)$ in the MST along with its weight and calculate the total weight of the MST.

## Example

**Input:**
```plaintext
Enter number of vertices: 5
Enter the adjacency matrix (5x5) row by row (0 if no edge):
0 2 0 6 0
2 0 3 8 5
0 3 0 0 7
6 8 0 0 9
0 5 7 9 0
```

**Output:**
```plaintext
--- Minimum Spanning Tree (MST) ---
Edge 	Weight
0 - 1	2
1 - 2	3
0 - 3	6
1 - 4	5
-----------------------------------
Total MST Weight: 16
```

## Complexity
- **Time Complexity:**
  - **Best Case:** $O(V^2)$
  - **Average Case:** $O(V^2)$
  - **Worst Case:** $O(V^2)$
  where $V$ is the number of vertices (using adjacency matrix representation).
- **Space Complexity:**
  - $O(V^2)$ for the graph adjacency matrix representation, and $O(V)$ auxiliary space for `parent`, `key`, and `inMST` arrays.

## Conclusion
The experiment successfully implements Prim's algorithm in Java. It constructs a Minimum Spanning Tree by greedily growing a tree from an arbitrary starting vertex, demonstrating optimal substructure and efficient sub-network design.
