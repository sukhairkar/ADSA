# Experiment 02: Implementation of a Hash Function

## Aim
To implement a hash function using the division method and handle collisions using linear probing in a fixed-size hash table.

## Requirements
- Java JDK 8 or later
- Command Prompt, PowerShell, VS Code, IntelliJ IDEA, or any Java-compatible IDE

## How to Compile
```bash
javac HashFunctionExp.java
```

## How to Run
```bash
java HashFunctionExp.java
```

## Algorithm
1. Initialize a hash table array of given capacity $m$ with all slots marked as empty (`-1`).
2. For each key $k$ to be inserted:
   - Compute the hash index using the division method: $h(k) = (k \bmod m + m) \bmod m$.
   - If the slot at index $h(k)$ is empty (`-1`), store the key at that index.
   - If a collision occurs (slot is already occupied), perform linear probing:
     - Sequentially check subsequent slots $(h(k) + i) \bmod m$ for $i = 1, 2, \dots$ until an empty slot is encountered or the search wraps around to the starting index.
     - If an empty slot is found, store the key; if all slots are full, report that the hash table is full.
3. Display the contents of each bucket index in the hash table.

## Example

**Input:**
```plaintext
Enter size of hash table: 7
Enter number of keys to insert: 5
Enter 5 integer keys:
10 20 5 15 22
```

**Output:**
```plaintext
Inserted 10 at index 3
Inserted 20 at index 6
Inserted 5 at index 5
Inserted 15 at index 1
Inserted 22 at index 2

Hash Table Contents:
Index 0: Empty
Index 1: 15
Index 2: 22
Index 3: 10
Index 4: Empty
Index 5: 5
Index 6: 20
```

## Complexity
- **Time Complexity:**
  - **Best Case:** $O(1)$ (direct slot access without collision)
  - **Average Case:** $O(1)$ (low load factor with few collisions)
  - **Worst Case:** $O(m)$ (table is heavily loaded, requiring full traversal of table capacity $m$)
- **Space Complexity:** $O(m)$ auxiliary space for table storage where $m$ is the capacity

## Conclusion
The experiment successfully implements a hash function using the division method with linear probing for collision resolution in Java. The results demonstrate how open addressing systematically resolves hash collisions and ensures near constant-time key insertion under low load factors.
