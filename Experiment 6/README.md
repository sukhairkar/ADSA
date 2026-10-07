# Experiment 06: Implement the Optimal Storage on Tape Algorithm

## Aim
To implement the Optimal Storage on Tape algorithm using a greedy approach and compute the storage order for a set of program lengths so that the Mean Retrieval Time (MRT) is minimised.

## Requirements
- Java JDK 8 or later
- Command Prompt, PowerShell, VS Code, IntelliJ IDEA, or any Java-compatible IDE

## How to Compile
```bash
javac OptimalStorageOnTape.java
```

## How to Run
```bash
java OptimalStorageOnTape.java
```

## Algorithm
1. Read the number of programs $n$ and their individual tape lengths $L_1, L_2, \dots, L_n$.
2. Formulate program objects storing their original ID and length.
3. Apply the **Greedy Choice**:
   - Sort the programs in non-decreasing (ascending) order of their lengths ($L_{(1)} \le L_{(2)} \le \dots \le L_{(n)}$).
4. Compute retrieval times:
   - The time to retrieve program at position $i$ is cumulative sum of lengths up to $i$: $T_i = \sum_{j=1}^{i} L_{(j)}$.
   - Total Retrieval Time $T_{\text{total}} = \sum_{i=1}^{n} T_i = \sum_{j=1}^{n} (n - j + 1) L_{(j)}$.
5. Calculate the Mean Retrieval Time (MRT):
   $$\text{MRT} = \frac{T_{\text{total}}}{n}$$
6. Display the optimal sequence order, per-program retrieval times, total retrieval time, and the resulting MRT.

## Example

**Input:**
```plaintext
Enter total number of programs: 3
Enter the lengths of 3 programs (space-separated):
5 10 3
```

**Output:**
```plaintext
-------------------------------------------
Optimal Storage Order: P3 -> P1 -> P2

Retrieval Time Breakdown:
Time to retrieve P3 (length 3): 3
Time to retrieve P1 (length 5): 8
Time to retrieve P2 (length 10): 18
-------------------------------------------
Total Retrieval Time : 29.00
Mean Retrieval Time (MRT): 9.67
-------------------------------------------
```

## Complexity
- **Time Complexity:**
  - **Best Case:** $O(n \log n)$ (dominated by the sorting step)
  - **Average Case:** $O(n \log n)$
  - **Worst Case:** $O(n \log n)$
- **Space Complexity:** $O(n)$ auxiliary space to store programs and their lengths

## Conclusion
The experiment successfully implements the Optimal Storage on Tape algorithm in Java. By sorting programs in ascending order of their lengths using a greedy strategy, the coefficient weight of each program in cumulative retrieval is minimized, yielding the minimum Mean Retrieval Time (MRT).
