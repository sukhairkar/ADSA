# Experiment 10: Floyd-Warshall All-Pairs Shortest Path Algorithm

## Aim
To implement the Floyd-Warshall algorithm for computing shortest paths between every pair of vertices in a weighted graph using an adjacency matrix input.

## Requirements
- Java JDK 8 or later
- Command Prompt, PowerShell, VS Code, IntelliJ IDEA, or any Java-compatible IDE

## How to Compile
```bash
javac FloydWarshallAllPairs.java
```

## How to Run
```bash
java FloydWarshallAllPairs.java
```

## Algorithm
1. Read the number of vertices $V$ and the initial $V \times V$ weighted adjacency matrix $D^{(0)}$, where $D[i][i] = 0$, $D[i][j] = \text{weight}(i, j)$, and $D[i][j] = \text{INF}$ (99999) if no direct path exists.
2. Execute three nested loops:
   - For every intermediate vertex $k$ from $0$ to $V - 1$:
     - For every source vertex $i$ from $0$ to $V - 1$:
       - For every destination vertex $j$ from $0$ to $V - 1$:
         - Check if the path through intermediate vertex $k$ is shorter than the direct path:
           $$\text{If } D[i][k] + D[k][j] < D[i][j] \text{ and neither term is INF:}$$
           $$D[i][j] = D[i][k] + D[k][j]$$
3. Display the final all-pairs shortest path distance matrix $D^{(V)}$, printing `INF` for pairs that cannot be reached.

## Example

**Input:**
```plaintext
Enter number of vertices: 4
Enter the adjacency matrix (4x4) row by row:
(Use 0 for self-loops, and 99999 if no direct edge exists)
0 3 99999 7
8 0 2 99999
5 99999 0 1
2 99999 99999 0
```

**Output:**
```plaintext
-------------------------------------------------
All-Pairs Shortest Path Distance Matrix (D^4):
-------------------------------------------------
      V0    V1    V2    V3    
V0    0     3     5     6     
V1    5     0     2     3     
V2    3     6     0     1     
V3    2     5     7     0     
-------------------------------------------------
```

## Complexity
- **Time Complexity:**
  - **Best Case:** $O(V^3)$
  - **Average Case:** $O(V^3)$
  - **Worst Case:** $O(V^3)$
  owing to the three nested loops running $V$ times each.
- **Space Complexity:** $O(V^2)$ to store the distance matrix.

## Conclusion
The experiment successfully implements the Floyd-Warshall algorithm using dynamic programming in Java. By systematically assessing every vertex as a potential intermediate hop, it finds the shortest paths between all pairs of vertices in $O(V^3)$ time complexity.
