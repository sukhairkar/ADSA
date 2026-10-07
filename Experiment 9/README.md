# Experiment 09: Dijkstra's Shortest Path Algorithm

## Aim
To find the shortest paths from a single source vertex to all others in a weighted graph using Dijkstra's algorithm.

## Requirements
- Java JDK 8 or later
- Command Prompt, PowerShell, VS Code, IntelliJ IDEA, or any Java-compatible IDE

## How to Compile
```bash
javac DijkstraShortestPath.java
```

## How to Run
```bash
java DijkstraShortestPath.java
```

## Algorithm
1. Initialize an array `dist[]` of size $V$ with $\infty$ (`Integer.MAX_VALUE`) and a boolean array `sptSet[]` of size $V$ with `false`.
2. Set distance to the chosen source vertex `dist[src] = 0`.
3. Loop $V - 1$ times:
   - Select vertex $u$ not yet included in `sptSet` having the minimum `dist[u]` value.
   - If no valid vertex is found, break.
   - Mark $u$ as processed (`sptSet[u] = true`).
   - For all adjacent vertices $v$ of $u$:
     - If $v$ is not yet in `sptSet`, an edge $(u, v)$ exists ($\text{graph}[u][v] \neq 0$), $\text{dist}[u] \neq \infty$, and $\text{dist}[u] + \text{graph}[u][v] < \text{dist}[v]$:
       - Update $\text{dist}[v] = \text{dist}[u] + \text{graph}[u][v]$.
4. Print the final computed shortest distance from the source vertex to every vertex in the graph.

## Example

**Input:**
```plaintext
Enter number of vertices: 5
Enter adjacency matrix (5x5) row by row (0 if no path):
0 10 0 30 100
10 0 50 0 0
0 50 0 20 10
30 0 20 0 60
100 0 10 60 0
Enter source vertex (0 to 4): 0
```

**Output:**
```plaintext
-------------------------------------------
Shortest Distances from Source Vertex: 0
Vertex 	 Shortest Distance
0 	 0
1 	 10
2 	 50
3 	 30
4 	 60
-------------------------------------------
```

## Complexity
- **Time Complexity:**
  - **Best Case:** $O(V^2)$
  - **Average Case:** $O(V^2)$
  - **Worst Case:** $O(V^2)$
  where $V$ is the number of vertices (using adjacency matrix representation).
- **Space Complexity:**
  - $O(V^2)$ for the adjacency matrix representation and $O(V)$ auxiliary space for `dist` and `sptSet` arrays.

## Conclusion
The experiment successfully implements Dijkstra's algorithm in Java. It determines the single-source shortest paths on non-negatively weighted graphs using a greedy relaxation strategy, showing reliable and optimal cost calculation across the network.
