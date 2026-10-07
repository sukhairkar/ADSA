# Experiment 08: Longest Common Subsequence (LCS) using Dynamic Programming

## Aim
To implement the Longest Common Subsequence (LCS) algorithm for two input strings and output the longest matching subsequence using dynamic programming.

## Requirements
- Java JDK 8 or later
- Command Prompt, PowerShell, VS Code, IntelliJ IDEA, or any Java-compatible IDE

## How to Compile
```bash
javac LCS_DynamicProgramming.java
```

## How to Run
```bash
java LCS_DynamicProgramming.java
```

## Algorithm
1. Read two input strings $s_1$ and $s_2$ of lengths $m$ and $n$ respectively.
2. Construct a 2D integer table `dp` of dimensions $(m + 1) \times (n + 1)$, initializing base conditions $\text{dp}[0][j] = 0$ and $\text{dp}[i][0] = 0$.
3. Compute table values bottom-up using the recurrence relation:
   - For $i = 1$ to $m$ and $j = 1$ to $n$:
     - If $s_1[i-1] == s_2[j-1]$, then $\text{dp}[i][j] = \text{dp}[i-1][j-1] + 1$.
     - Else, $\text{dp}[i][j] = \max(\text{dp}[i-1][j], \text{dp}[i][j-1])$.
4. Backtrack through the DP matrix starting at cell $(m, n)$ down to $(0, 0)$ to reconstruct the LCS characters:
   - If $s_1[i-1] == s_2[j-1]$, append the character to result and move diagonally to $(i-1, j-1)$.
   - Else if $\text{dp}[i-1][j] > \text{dp}[i][j-1]$, move up to $(i-1, j)$.
   - Else, move left to $(i, j-1)$.
5. Reverse the reconstructed string to obtain the LCS in correct order.
6. Print the length of the LCS, the LCS string, and the populated dynamic programming matrix table.

## Example

**Input:**
```plaintext
Enter first string : LONGEST
Enter second string: STONE
```

**Output:**
```plaintext
-------------------------------------------
Length of Longest Common Subsequence: 3
Longest Common Subsequence (LCS)    : ONE
-------------------------------------------

--- Dynamic Programming Table ---
      S  T  O  N  E  
   0  0  0  0  0  0 
L  0  0  0  0  0  0 
O  0  0  0  1  1  1 
N  0  0  0  1  2  2 
G  0  0  0  1  2  2 
E  0  0  0  1  2  3 
S  0  1  1  1  2  3 
T  0  1  2  2  2  3 
```

## Complexity
- **Time Complexity:**
  - **Best Case:** $O(m \times n)$
  - **Average Case:** $O(m \times n)$
  - **Worst Case:** $O(m \times n)$
  where $m$ and $n$ are the lengths of the two input strings. Backtracking step takes $O(m + n)$.
- **Space Complexity:** $O(m \times n)$ auxiliary space for the 2D DP matrix table.

## Conclusion
The experiment successfully implements the Longest Common Subsequence algorithm using dynamic programming in Java. The bottom-up tabulation approach overcomes the exponential time complexity of pure recursion, solving subproblems in polynomial time and accurately extracting the longest subsequence.
