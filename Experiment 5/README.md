# Experiment 05: Implement Breadth First Search Graph Traversal

## Aim
To implement Breadth First Search (BFS) graph traversal for directed and undirected graphs using an adjacency list and a queue.

## Requirements
- Java JDK 8 or later
- Command Prompt, PowerShell, VS Code, IntelliJ IDEA, or any Java-compatible IDE

## How to Compile
```bash
javac BFS_Traversal.java
```

## How to Run
```bash
java BFS_Traversal.java
```

## Algorithm
1. Represent the graph using an array of `LinkedList<Integer>` of size $V$ (adjacency list representation).
2. For each edge $(u, v)$ entered by user, add $v$ to $u$'s list. If the graph is undirected, also add $u$ to $v$'s list.
3. Initialize a boolean array `visited` of size $V$ with all values set to `false`, and create a FIFO queue.
4. Mark the user-selected starting vertex as visited (`visited[start] = true`) and insert it into the queue.
5. While the queue is not empty:
   - Dequeue front vertex $u$ and print it.
   - For every neighbor $v$ in `adj[u]`:
     - If `visited[v]` is `false`:
       - Mark `visited[v] = true`.
       - Enqueue $v$.
6. Terminate when the queue becomes empty.

## Example

**Input:**
```plaintext
Enter total number of vertices: 4
Enter total number of edges: 4
Is the graph directed? (true/false): false
Enter each edge as: <source> <destination> (0 to 3):
0 1
0 2
1 2
2 3
Enter start vertex for BFS traversal: 0
```

**Output:**
```plaintext
BFS Traversal Order: 0 1 2 3 
```

## Complexity
- **Time Complexity:**
  - **Best Case:** $O(V + E)$
  - **Average Case:** $O(V + E)$
  - **Worst Case:** $O(V + E)$
  where $V$ is the number of vertices and $E$ is the number of edges.
- **Space Complexity:**
  - $O(V)$ auxiliary space for the `visited` array and queue buffer, plus $O(V + E)$ space for the adjacency list representation.

## Conclusion
The experiment successfully implements Breadth First Search (BFS) graph traversal in Java. It illustrates level-order vertex exploration using a FIFO queue, ensuring that all vertices at distance $k$ from the source are explored before vertices at distance $k+1$.
